---
# An instance of the Contact widget.
widget: contact

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 60

title: Contact
subtitle:

content:
  # Automatically link email and phone or display as text?
  autolink: true

  # Email form provider
  form:
    provider: netlify
    formspree:
      id:
    netlify:
      # Enable CAPTCHA challenge to reduce spam?
      captcha: false

  # Contact details (edit or remove options as required)
  email: mdsadilkhan99@gmail.com
  phone: '+33751900239'
  # address:
  #   street: 20 Avenue Albert Einstein
  #   city: Villeurbanne
  #   postcode: '69100'
  #   country: France
  #   country_code: FR
  # coordinates:
  #   latitude: '37.4275'
  #   longitude: '-122.1697'
  # directions: Enter Building 1 and take the stairs to Office 200 on Floor 2
  # office_hours:
   # - 'Monday 10:00 to 13:00'
    #- 'Wednesday 09:00 to 10:00'
  #appointment_url: 'https://calendly.com'
  contact_links:
    - icon: linkedin
      icon_pack: fab
      name: Connect Here
      link: https://www.linkedin.com/in/mohammad-sadil-khan-a96568170/
  
  #   - icon: twitter
  #     icon_pack: fab
  #     name: DM Me
  #     link: 'https://twitter.com/Twitter'
  #   - icon: video
  #     icon_pack: fas
  #     name: Zoom Me
  #     link: 'https://zoom.com'

design:
  columns: '2'
---
