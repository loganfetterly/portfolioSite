<template>
  <core-section id="lets-talk">
    <core-heading>Let's talk.</core-heading>

    <v-col
      cols="12"
      md="5"
      class="mb-4 pr-md-5"
    >
      <core-subheading class="text-uppercase">
        What can I do for you?
      </core-subheading>

      <core-text class="mb-5">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
        Fusce vel est interdum, pharetra magna ac, facilisis ante.
        Fusce eu finibus magna. Sest interdum, pharetra magna ac, facilisis ante.
        Fusce eu finibus magna.
      </core-text>

      <core-subheading class="text-uppercase mb-5">
        Send me a Message
      </core-subheading>

      <v-form>
        <v-text-field
          solo-inverted
          flat
          label="Name"
        />

        <v-text-field
          solo-inverted
          flat
          label="Email"
        />

        <v-text-field
          solo-inverted
          flat
          label="Subject"
        />

        <v-textarea
          id="brokenInput"
          solo-inverted
          flat
          label="Message"
        />

        <v-btn
          class="ma-0"
          color="primary"
        >
          <a v-bind="insertEmail">CONTACT ME</a>
        </v-btn>
      </v-form>
    </v-col>

    <v-col
      cols="12"
      md="4"
      class="text-left"
    >
      <core-subheading class="text-uppercase">
        Social Contacts
      </core-subheading>

      <social-contacts />

      <v-list
        class="transparent"
        three-line
      >
        <v-list-item>
          <v-list-item-avatar>
            <v-icon
              class="mr-5 sIcons"
              color="primary"
              size="36"
            >
              mdi-map-marker
            </v-icon>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title class="primary--text">
              Address
            </v-list-item-title>
            <v-list-item-subtitle>
              {{ schema.basics.location.address }}<br>
              {{ schema.basics.location.city }}, {{ schema.basics.location.postalCode }}
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-avatar>
            <v-icon
              size="36"
              color="primary"
              class="mr-5 sIcons"
            >
              mdi-email
            </v-icon>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title class="primary--text">
              Email
            </v-list-item-title>
            <v-list-item-subtitle v-text="schema.basics.email" />
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-avatar>
            <v-icon
              size="36"
              color="primary"
              class="mr-5 sIcons"
            >
              mdi-phone
            </v-icon>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title class="primary--text">
              Phone
            </v-list-item-title>
            <v-list-item-subtitle v-text="schema.basics.phone" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-col>
  </core-section>
</template>

<script>
  // Utilities
  import {
    mapState,
  } from 'vuex'

  export default {
    name: 'LetsTalk',

    components: {
      SocialContacts: () => import('@/components/SocialContacts'),
    },

    computed: {
      ...mapState('app', ['schema']),

      insertEmail () {
        return {
          id: 'contactButton',
          href: 'mailto:lfetterly25@gmail.com',
        }
      },
    },
  }
</script>

<style>

#brokenInput:focus {
  color: rgb(118, 118, 118);
}

.sIcons {
  padding-left: 20px;
}

#contactButton {
  color: white;
  text-decoration: none;
}

#lets-talk {
  margin-top: 350px;
}

</style>
