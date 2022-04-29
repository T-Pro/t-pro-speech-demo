# t-pro-speech-demo

T-PRO offers simplified interface for high quality online speech recognition for interactive applications as well as transcriptions of recorded files.

`https://rexapi.tpro.rocks` exposes endpoints that you can use for managing client metadata, `https://rexws.tpro.rocks` allows to send audio and retrieving speech recognition results.

This sample shows how simple it can be to get you up and running

  1. You authenticate and get a the user details, that includes, settings and the user token that will be used to do other calls.
  2. You create a socket.io connection to `https//rexws.tpro.rocks` with the token you received after login.
  3. You create a dictation specifying `type: 'frontend'`, as opposed to `backend` meant to non-interactive applications.
  4. `init` let's the server know that you are going to start sending audio
  5. `start`/`stop` as many time as you want.
  6. `stop` makes sure that the server retrieves the results as soon as possible, while if you are continuously recording it may wait a little before sending the result, maybe you are only breathing or thinking about what to say next.
  7. As you say the audio you will receive events with the results of the speech recognition.
  8. You will receive previews, and eventually final results.
  9. The final corresponds to non-overlapping segments of your audio, while the preview is meant to give a low latency feedback about the ongoing utterance.


