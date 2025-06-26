# ProjectedTurefCoordinatesToGeographic

This package is a .NET library designed for transformation coordinates from projected systems to geographic coordinates.  
It works in harmony with NetTopologySuite and ProjNet libraries, facilitating the conversion from TUREF(Turkish Reference Frame) TM (Transverse Mercator) projection to geographic coordinate systems.

---

## Features

- Transformation from TM projection to geographic coordinate system  
- Single and batch geometry transformations  
- Well-Known Text (WKT) format support compatible with NetTopologySuite  
- GRS80 ellipsoid support
- Supports only Turkiye's TUREF TM projection and 2D geometries
- Supported TUREF TM projections include:;
	-TUREF / TM27 (EPSG: 5253)
	-TUREF / TM30 (EPSG: 5254)
	-TUREF / TM33 (EPSG: 5255)
	-TUREF / TM36 (EPSG: 5256)
	-TUREF / TM39 (EPSG: 5257)
	-TUREF / TM42 (EPSG: 5258)
	-TUREF / TM45 (EPSG: 5259)
- Needs NetTopologySuite version: 2.6.0
- Needs ProjNet version: 2.0.0

---

## Installation

Use the NuGet package manager:

```bash
dotnet add package ProjectedTurefCoordinatesToGeographic --version 1.0.0
```
---

## UsageExamples

### Single Geometry Transformation

```csharp
var input = new InputEntityDto
{
    ProjectedWKT = "POLYGON((...))",
    CentralMeridian = 33
};

string geographicWkt = GeometryConverter.ConvertTmToGeographic(input);
// 'geographicWkt' now contains the geometry in geographic coordinate system as WKT.
```

### Batch Geometry Transformation

```csharp
var list = new List<InputEntityDto> { input, /* other inputs */ };

List<string> results = GeometryConverter.ConvertMultipleTmToGeographic(list);

// The 'results' list contains the geographic coordinate transformations for each input.
```
---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

## Contributing

Contributions are welcome! Please open a pull request or issue for feedback and improvements.

---

## Contact

For any questions or issues, please open an issue on the GitHub repository or contact the project maintainers.

- Developer: Oğuzhan Candemir
- Email: candemiroguz@outlook.com
- GitHub: https://github.com/candemiroguz