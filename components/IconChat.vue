<template>
  <div class="w-100 d-flex flex-column align-items-end innerdiv">
    <div id="popover-1-div" style="font-size: 2rem;">
      <b-icon icon="chat" class="rounded-circle bg-danger p-2 cursor" variant="light"></b-icon>
    </div>

    <b-popover
      :show.sync="show"
      target="popover-1-div"
      placement="auto"
      triggers="hover focus"
      custon-class="maxH"
    >
      <div class="maxSize">
        <Chat
          :participants="participants"
          :myself="myself"
          :messages="messages"
          :chat-title="chatTitle"
          :placeholder="placeholder"
          :colors="colors"
          :border-style="borderStyle"
          :hide-close-button="true"
          :close-button-icon-size="closeButtonIconSize"
          :submit-icon-size="submitIconSize"
          :load-more-messages="toLoad.length > 0 ? loadMoreMessages : null"
          :async-mode="asyncMode"
          :scroll-bottom="true"
          :display-header="true"
          :send-images="true"
          :profile-picture-config="profilePictureConfig"
          :timestamp-config="timestampConfig"
          :link-options="linkOptions"
          :accept-image-types="'.png, .jpeg'"
          @onImageClicked="onImageClicked"
          @onImageSelected="onImageSelected"
          @onMessageSubmit="onMessageSubmit"
          @onType="onType"
        />
      </div>
    </b-popover>
    <Assist />
  </div>
</template>

<script>
import { Chat } from "vue-quick-chat";
import "vue-quick-chat/dist/vue-quick-chat.css";

export default {
  components: {
    Chat
  },
  props: {
    show: Boolean
  },
  data() {
    return {
      visible: true,
      participants: [
        {
          name: "Arnaldo",
          id: 1,
          profilePicture:
            "https://upload.wikimedia.org/wikipedia/en/thumb/a/a1/NafSadh_Profile.jpg/768px-NafSadh_Profile.jpg"
        }
      ],
      myself: {
        name: "Matheus S.",
        id: 3,
        profilePicture:
          "https://lh3.googleusercontent.com/-G1d4-a7d_TY/AAAAAAAAAAI/AAAAAAAAAAA/AAKWJJPez_wX5UCJztzEUeCxOd7HBK7-jA.CMID/s83-c/photo.jpg"
      },
      messages: [],
      chatTitle: "Atendimento via Chat",
      placeholder: "Envie sua mensagem",
      colors: {
        header: {
          bg: "#808080",
          text: "#fff"
        },
        message: {
          myself: {
            bg: "#20B2AA",
            text: "#fff"
          },
          others: {
            bg: "#D3D3D3",
            text: "#808080"
          },
          messagesDisplay: {
            bg: "#f7f3f3"
          }
        },
        submitIcon: "#808080",
        submitImageIcon: "#808080"
      },
      borderStyle: {
        topLeft: "3px",
        topRight: "3px",
        bottomLeft: "3px",
        bottomRight: "3px"
      },
      hideCloseButton: true,
      submitIconSize: 25,
      closeButtonIconSize: "20px",
      asyncMode: false,
      toLoad: [
        {
          content: "Qual o prezo de entrega?",
          myself: true,
          participantId: 3,
          timestamp: {
            year: 2018,
            month: 1,
            day: 26,
            hour: 10,
            minute: 10,
            second: 3,
            millisecond: 123
          },
          uploaded: true,
          viewed: true,
          type: "text"
        },
        {
          content:
            "Hey, obrigado por aguardar, Você está senda transferido para um operador. O Número de seu procolo é 322265.",
          myself: false,
          participantId: 1,
          timestamp: {
            year: 2018,
            month: 1,
            day: 26,
            hour: 10,
            minute: 11,
            second: 3,
            millisecond: 123
          },
          uploaded: true,
          viewed: false,
          type: "text"
        },
        {
          content:
            "Hey, o prazo de entrega para a região sudeste tem previsção de no máximo 07 dias úteis.",
          myself: false,
          participantId: 1,
          timestamp: {
            year: 2018,
            month: 1,
            day: 26,
            hour: 10,
            minute: 12,
            second: 3,
            millisecond: 123
          },
          uploaded: true,
          viewed: true,
          type: "text"
        },
        {
          content: "Obrigado",
          myself: true,
          participantId: 3,
          timestamp: {
            year: 2018,
            month: 1,
            day: 26,
            hour: 10,
            minute: 13,
            second: 3,
            millisecond: 123
          },
          uploaded: true,
          viewed: true,
          type: "text"
        }
      ],
      scrollBottom: {
        messageSent: true,
        messageReceived: true
      },
      displayHeader: true,
      profilePictureConfig: {
        others: false,
        myself: false,
        styles: {
          width: "30px",
          height: "30px",
          borderRadius: "50%"
        }
      },
      timestampConfig: {
        format: "DD 'às' HH:mm",
        relative: false
      },
      // there are other options, you can check them here
      // https://soapbox.github.io/linkifyjs/docs/options.html
      linkOptions: {
        myself: {
          className: "myLinkClass",
          events: {
            click: function(e) {
              alert("Link clicked!");
            },
            mouseover: function(e) {
              alert("Link hovered!");
            }
          },
          format: function(value, type) {
            if (type === "url" && value.length > 50) {
              value = value.slice(0, 50) + "…";
            }
            return value;
          }
        },
        others: {
          className: "othersLinkClass",
          events: {
            click: function(e) {
              alert("Link clicked!");
            },
            mouseover: function(e) {
              alert("Link hovered!");
            }
          },
          format: function(value, type) {
            if (type === "url" && value.length > 50) {
              value = value.slice(0, 50) + "…";
            }
            return value;
          }
        }
      }
    };
  },
  methods: {
    onType: function(event) {
      //here you can set any behavior
    },
    loadMoreMessages(resolve) {
      setTimeout(() => {
        resolve(this.toLoad); //We end the loading state and add the messages
        //Make sure the loaded messages are also added to our local messages copy or they will be lost
        this.messages.unshift(...this.toLoad);
        this.toLoad = [];
      }, 1000);
    },
    onMessageSubmit: function(message) {
      /*
       * example simulating an upload callback.
       * It's important to notice that even when your message wasn't send
       * yet to the server you have to add the message into the array
       */
      this.messages.push(message);

      /*
       * you can update message state after the server response
       */
      // timeout simulating the request
      setTimeout(() => {
        message.uploaded = true;
      }, 2000);
    },
    onImageSelected(files, message) {
      let src =
        "https://149364066.v2.pressablecdn.com/wp-content/uploads/2017/03/vue.jpg";
      this.messages.push(message);
      /**
       * This timeout simulates a requisition that uploads the image file to the server.
       * It's up to you implement the request and deal with the response in order to
       * update the message status and the message URL
       */
      setTimeout(
        res => {
          message.uploaded = true;
          message.src = res.src;
        },
        3000,
        { src }
      );
    },
    onImageClicked(message) {
      /**
       * This is the callback function that is going to be executed when some image is clicked.
       * You can add your code here to do whatever you need with the image clicked. A common situation is to display the image clicked in full screen.
       */
      console.log("Image clicked", message.src);
    }
  }
};
</script>

<style scoped>
.innerdiv {
  position: relative;
  float: right;
  right: 1em;
  top: 0;
  margin-bottom: 2em;
  margin-top: 2em;
  z-index: 200;
}

.popover .maxSize {
  max-width: 300px;
  max-height: 350px !important;
}

.quick-chat-container {
  max-height: 330px !important;
}

.cursor {
  cursor: pointer;
}
</style>
