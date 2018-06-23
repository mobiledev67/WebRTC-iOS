# WebRTC-iOS
A simple native WebRTC demo iOS app using swift 

## Requirments
1. Xcode 9.4 or newer
2. Cocoapods
3. Node.js + npm


## Setup instructions
1. Start the signaling server:
    1. Navigate to the `signaling` folder
    2. Run `npm install` to install all dependencies
    3. Run `node app.js` to start the server
2. Run `pod install` from the WebRTC app, where you find the `WebRTC.xcworkspace` file.
3. Modify `SignalClient.swift` and set the `serverUrl` variable to your signaling server ip/host. Don't use `localhost` or `127.0.0.1` if you plan to connect other devices in your network to your mac.
4. Build and run on devices or simulator (video capture is not supported on a simulator).

## Run instructions
1. Run the app one two devices with the signaling server running
2. Make sure both of the devices are connected to the signaling server
3. On the first device, click on 'Send offer' - this will generate local offer SDP and send it to the other client using the signaling server
4. Wait until the second device receives the offer from the first device (you should see that a remote SDP has arrived)
5. Click on 'Send answer' on the second device
6. when the answer arrives to the first device, both of the devices should be now connected to each other using webRTC, try to talk or click on the 'video' button to start capturing video.
7. To restart the process, kill both apps and do steps 1-6 once again

## References:
* WebRTC website: https://webrtc.org/
* WebRTC iOS compile guide: https://webrtc.org/native-code/ios/
* appear.in dev blog post: https://github.com/appearin/tech.appear.in/blob/master/source/_posts/Getting-started-with-WebRTC-on-iOS.md (it uses old WebRTC api but still very informative)
* AppRTC - a more detailed app to demonstrate WebRTC: https://github.com/ISBX/apprtc-ios
* Useful information from pexip: https://pexip.github.io/pexkit-sdk/ios_media
