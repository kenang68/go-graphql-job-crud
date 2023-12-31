GO GRAPHQL JOB CRUD

Mod init your project, give it whatever name you like go mod init github.com/kenang68/go-graphql-job-crud
Get all the dependencies go mod tidy

Initialize your project go run github.com/99designs/gqlgen init
After you've written the graphql schema, run this - go run github.com/99designs/gqlgen generate

After you've built the project, run this - go run server.go

The database used here is MongoDB. For this example, it is installed in localhost.

These are the queries examples to interact with the API -

Get All Jobs
query GetAllJobs{ jobs{ \_id title description company url } }

=======================

Create Job
mutation CreateJobListing($input: CreateJobListingInput!){ createJobListing(input:$input){ \_id title description company url } }

{ "input": { "title": "Software Development Engineer - I", "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt", "company": "Google", "url": "www.google.com/" } }

=========================

Get Job By Id
query GetJob($id: ID!){ job(id:$id){ \_id title description url company } }

{ "id": "638051d7acc418c13197fdf7" }

=========================

Update Job By Id
mutation UpdateJob($id: ID!,$input: UpdateJobListingInput!) { updateJobListing(id:$id,input:$input){ title description \_id company url } }

{ "id": "638051d3acc418c13197fdf6", "input": { "title": "Software Development Engineer - III" } }

=================================

Delete Job By Id
mutation DeleteQuery($id: ID!) { deleteJobListing(id:$id){ deletedJobId } }

{ "id": "638051d3acc418c13197fdf6" }
