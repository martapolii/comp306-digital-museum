## Getting started

Open `DigitalMuseum.slnx` in Visual Studio and build the solution. Run
`DigitalMuseum.Api` and open Swagger at https://localhost:7147/swagger.
Run `DigitalMuseum.Web` and open https://localhost:7109/.

For tasks #5–7, add `SubmissionsController` to `DigitalMuseum.Api` and
build the Contributor Portal and curator review screens in
`DigitalMuseum.Web`. Put persistence code in `DigitalMuseum.Data`.

The API currently exposes the sample WeatherForecast endpoint, and the
web app shows the default MVC home page. Once `GET /api/exhibits` is
available, use it to populate the contributor form’s exhibit selector.