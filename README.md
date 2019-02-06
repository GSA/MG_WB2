# Well-Built for Wellbeing (WB2)
From 2016-17, GSA's Office of [Federal High Performance Buildings](https://www.gsa.gov/about-us/organization/office-of-governmentwide-policy/office-of-federal-highperformance-buildings) collected Indoor Environmental Air Quality data in several of GSA's buidlings. This data is stored in a number of csvs. This repo contains the ETL scripts to dump that data into a Microsoft SQL Server.

## Getting Started
Download the data [here](https://drive.google.com/drive/u/0/folders/1Ah7MOw99aKeQazV5bOAxG8r0zR4jHI5r). Move the two zip files into the data directory within this repo's root directory. Unzip those two files and then unzip all of the csvs within. You can do so in Linux or OSX with:
```bash
cd 2016
gunzip *.gz
```

## License

This project is licensed under the Creative Commons Zero v1.0 Universal License - see the [LICENSE.md](https://github.com/GSA/wb2/blob/master/LICENSE) file for details
