---
swagger: "2.0"
x-collection-name: GoToMeeting
x-complete: 0
info:
  title: Go To Training Create Training
  description: Schedules a training of one or more sessions. The call requires a training's
    name, at least one start and end time, and optionally may include additional sessions,
    a description, additional organizers (presenters), and registration settings.
    You can only add organizers to a training if you have a multi-user account. Once
    a training has been created with this method, you can accept registrations to
    the training. Registration is for the entire training - all sessions. (The GoToTraining
    admin site enables you to create trainings that allow participants to register
    for individual sessions as well as automatically create weekly or monthly events.)
    Registration settings controls whether you allow web registration for this training,
    and whether a confirmation email is sent to the registrant following registration.
    Disabling the confirmation email is an API-only setting. If the user registers
    through the GoToTraining website, a confirmation email is sent. If the user is
    manually approved by the training administrator through the GoToTraining web site,
    the confirmation email is sent. It is recommended that you disable web registration
    if you disable confirmation emails. The response contains a trainingKey for the
    scheduled training.
  termsOfService: https://developer.citrixonline.com/terms-use
  contact:
    name: Developer Support
    url: https://developer.citrixonline.com
    email: developer-support@citrixonline.com
  version: 1.0.0
host: api.citrixonline.com
basePath: /G2T/rest
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /organizers/{organizerKey}/trainings:
    get:
      summary: Get Trainings
      description: This call retrieves information on all scheduled trainings for
        a given organizer. The trainings are returned in the order in which they were
        created. Completed trainings are not included; ongoing trainings with past
        sessions are included along with the past sessions. If the organizer does
        not have any scheduled trainings, the response will be empty.
      operationId: getAllTrainings
      x-api-path-slug: organizersorganizerkeytrainings-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
    post:
      summary: Create Training
      description: Schedules a training of one or more sessions. The call requires
        a training's name, at least one start and end time, and optionally may include
        additional sessions, a description, additional organizers (presenters), and
        registration settings. You can only add organizers to a training if you have
        a multi-user account. Once a training has been created with this method, you
        can accept registrations to the training. Registration is for the entire training
        - all sessions. (The GoToTraining admin site enables you to create trainings
        that allow participants to register for individual sessions as well as automatically
        create weekly or monthly events.) Registration settings controls whether you
        allow web registration for this training, and whether a confirmation email
        is sent to the registrant following registration. Disabling the confirmation
        email is an API-only setting. If the user registers through the GoToTraining
        website, a confirmation email is sent. If the user is manually approved by
        the training administrator through the GoToTraining web site, the confirmation
        email is sent. It is recommended that you disable web registration if you
        disable confirmation emails. The response contains a trainingKey for the scheduled
        training.
      operationId: scheduleTraining
      x-api-path-slug: organizersorganizerkeytrainings-post
      parameters:
      - in: body
        name: body
        description: The details of the training to create
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---