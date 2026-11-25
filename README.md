# Digital Museum Exhibit Management and Contributor Portal

Group 3 project for COMP 306 — API Engineering and Cloud Computing.

The Digital Museum gives visitors a place to explore educational exhibits, contributors a way to suggest new items, and curators a central place to review submissions and manage published content.

## Museum and Contributor Portals

| User | What they can do |
|---|---|
| Visitors | Browse exhibits and view individual artifacts, artworks, and specimens. |
| Contributors | Propose an item for an existing exhibit and check its status using a submission reference. |
| Curators | Create and manage exhibits and exhibit items, and approve or reject contributor submissions. |

The Museum Portal serves visitors and authorized curators. The shared Contributor Portal provides the submission form and status lookup.

## Exhibit Themes

| Subject | Initial themes |
|---|---|
| History | Ukrainian Cossacks (Kozaks) and the Ottoman Empire |
| Biology | Insects and dinosaurs |
| Art | Works by established and emerging artists |

An **exhibit** is a themed group of museum content, such as Dinosaurs. An **exhibit item** is an individual entry within that exhibit, such as a fossil specimen. A **submission** is a contributor’s proposal for a new exhibit item.

## Submission Workflow

1. A contributor selects an existing exhibit and submits a proposed item.
2. The system marks the submission as **Pending** and provides a reference number.
3. A curator reviews the submission and marks it **Approved** or **Rejected**.
4. An approved submission becomes an exhibit item in the selected exhibit. Rejected submissions retain their status so contributors can look them up.

## API and Technology

| Component | Planned implementation |
|---|---|
| Backend | C# and ASP.NET Core Web API with `ExhibitsController`, `ExhibitItemsController`, and `SubmissionsController` |
| API design | Repository pattern, at least three DTO classes per controller, and AutoMapper |
| Web client | Museum and Contributor Portals that call the API using `HttpClient` |
| Data and images | Amazon DynamoDB for records and Amazon S3 for exhibit item images |
| Deployment | Docker image stored in Amazon ECR and run as a standalone ECS Fargate task |
| API management | Google Apigee proxy with API key verification |

Each controller supports six actions: list all records, get one by ID, create (`POST`), replace (`PUT`), partially update (`PATCH`), and delete (`DELETE`). The web client will demonstrate all 18 actions across the three controllers.

## Task Breakdown

| Task | What it includes |
|---|---|
| 1. Exhibits | Build `ExhibitsController` and curator screens to create, view, edit, and delete exhibits. |
| 2. Exhibit items | Build `ExhibitItemsController` and curator screens to manage individual items within exhibits. |
| 3. Visitor pages | Let visitors browse History, Biology, and Art exhibits and view individual items. |
| 4. S3 images | Store exhibit item images in S3 and display them in the Museum Portal. |
| 5. Contributor Portal | Build the submission form with an existing exhibit selector and a status lookup by reference number. |
| 6. Submissions and curator review | Build `SubmissionsController` and the screen where curators review, approve, or reject submissions. |
| 7. Approval and publishing | Connect the approval workflow to exhibit item creation so approved items appear in the selected exhibit. |
| 8. Shared setup and testing | Set up DynamoDB, prepare sample data, configure curator access, and verify all 18 API actions through the web client. |
| 9. Cloud deployment and screenshots | Containerize the API, push the image to ECR, run it on ECS Fargate, configure Apigee, and capture the required screenshots. |
| 10. Report and live demo | Document the architecture, data model, and lessons learned. Prepare and rehearse the local demo. |

## Optional Features

- Search and filters by subject, period, or artist
- Email notifications when a submission’s status changes
- Individual contributor accounts and private submission dashboards
