# Użycie Entity

## Stworzenie Entity

```ts
@Exlude()
export class PublicServicePointsListForMapEntity {
    @Expose()
    @ApiProperty()
    id: number

    @Expose()
    @ApiProperty()
    @Type(() => ServicePointGeoLocalizationEntity)
    servicePointGeoLocalization: ServicePointGeoLocalizationEntity

    @Expose()
    @ApiProperty()
    @ApiPropertyOptional()
    @Type(() => ContactEntity)
    contact?: ContactEntity

    @Expose()
    @ApiPropertyOptional()
    @Type(() => AddressEntity)
    address?: AddressEntity

    @Expose()
    @ApiProperty()
    isPublic: boolean

    @Expose()
    @ApiProperty()
    name: boolean

    @Expose()
    @ApiProperty()
    description: boolean

    @Expose()
    @ApiProperty()
    @Type(() => ServicePointTemplateEntity)
    servicePointTemplate?: ServicePointTemplateEntity

    constructor(partial: Partial<ServicePointTemplateEntity>) {
        Object.assign(this, partial)
    }
}
```

## Użycie w Service
```ts
async getAllPublicServicePointsForMap(
    servicePointTemplateIds: number[]
): Promise<PublicServicePointsListForMapEntry[]> {
    const serviePoints = await this.prisma.servicePoint.findMany({
        where: {
            isPublic: true,
            NOT: {
                servicePointGeoLocalization: null,
            },
            servicePointTemplateId: { in: servicePointTemplateIds }
        },
        include: {
            servicePointTemplate: true,
            servicePointGeoLocalization: true,
            contact: true,
            address: true,
        }
    })

    return servicePoints.map(servicePoint = new PublicServicepointsListForMapEntity(servicePoint))
}
```

## Użycie w kontrolerze

```ts
@Get({ path: "map" })
@ApiOperation({ summary: "Get all public service points for map view (right now this returns all service points" })
@ServicePointTemplateIdsFromParamsApi()
@ApiResponse({ status: 200, type: PublicServicePointsListForMapEntity, })
async getAllPublicServicePointsForMap(
    @GetServicePointTemplateIdListFromParam() servicePointTemplateIds: number[],
): Promise<PublicServicePointsListEntity[]> {
    return this.servicePointService.getAllPublicServicePointsForMap(servicePointTemplateIds)
}
```