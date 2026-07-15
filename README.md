# Bürgewald Multispectral Sample Dataset

Multispectral drone imagery collected over the Bürgewald area near Jülich, Germany. Intended as a sample dataset for [OpenDroneMap](https://github.com/OpenDroneMap/ODM) and related projects.

## Dataset summary

| Field | Value |
| --- | --- |
| Location | Bürgewald, North Rhine-Westphalia, Germany (~50.86°N, 6.53°E) |
| Collection date | 2024-03-07 |
| Image captures | 762 |
| Image files | 4572 (6 spectral bands per capture) |
| Total size | ~18.5 GB |
| Image format | GeoTIFF |
| Image size | 1456 × 1088 px |
| Sensor | MicaSense RedEdge-P |
| Bands | Blue, Green, Red, NIR, Red edge, Panchro |
| EXIF GPS | Yes |
| GCP file | No |
| RTK | No |

## Structure

```
odm_data_buergewald/
├── README.md
├── LICENSE
└── images/
    ├── IMG_0000_1.tif
    ├── IMG_0000_2.tif
    └── ...
```

All band images for each capture are stored together in `images/`. File names follow the pattern `IMG_<capture>_<band>.tif`.

## Processing with ODM

Place this repository (or only its `images/` folder) in a project directory and run ODM as usual:

```bash
docker run -ti --rm -v /path/to/odm_data_buergewald:/datasets/project opendronemap/odm --project-path /datasets/project
```

For multispectral processing, include all band images and consider radiometric calibration:

```bash
--radiometric-calibration camera
```

See the [ODM multispectral documentation](https://docs.opendronemap.org/multispectral/) for details.

## License

This dataset is released under [CC0 1.0 Universal](LICENSE).

## Contributing to ODMData

To propose inclusion in the official [ODM datasets list](https://opendronemap.org/odm/datasets/), post in the [OpenDroneMap community forum](https://community.opendronemap.org/c/datasets/10) with a link to this repository.
