## CP+B Candidate Lab

Hello and thank you for taking the time to work on this lab!

This lab is an opportunity for us to have a conversation about practices, conventions, and workflow.
It will also help us better understand you as a developer.
Please use this as a way to communicate through your craft.


# Setup

1. Fork this repo and clone to your computer
2. Setup the project in your preferred IDE
3. View index.html in the browser (/www)
4. Open the psd file in /psd (/psd)


# Development

* Improve semantic structure and content of the HTML
* Incorporate missing design elements (per psd)
* Create an RSVP message onClick of 'Yes' or 'No':
  ** Provide feedback to the user with confirmation of their choice
  ** Design, behavior, and messaging are up to you
  ** Plug-ins, libraries, and frameworks are permitted
* Modify anything and everything you think should be different/improved. Document the reasoning for your changes in the Notes section.


# Workflow

Please make atomic commits (commit often) as you progress.
Be sure to provide useful commit messages to illustrate milestones and workflow.
Submit a pull request when you are finished and satisfied with your work.

# Notes

Use this area to communicate any thought processes, ideas, or challenges you encountered.

## Improve semantic structure and content of the HTML + CSS
* Decided not to add support for rounded borders for < IE9 because it is only required for the buttons
* Added favicon apple-icon-touch from polaroid web site

## Incorporate missing design elements (per psd)
* Added the two missing pics. Exported as png to get the transparency for responsive (different width)
* Added box-shadow for the invitation

##Creation of RSVP message
* Added a div element to present feedback to the user.
* Added JavaScript to handle the user response to the RSVP. A spinner is shown inside the clicked button. The spinner is shown for 2 seconds and then hidden. Then, a message is shown to confirm the user the result of the action
* Progresive Enhancement: if the user has disabled JavaScript, then she is redirected to a success or reject page

##Responsive Design
* Use of media-queries to re-arrange UI elements for mobile devices
