# React Hooks

A collection of custom react hooks.

## Documentation

[useRecord](https://github.com/ayush-rathore/react-hooks/blob/main/src/useRecord.js) - Custom hook to record audio via Expo Audio

[useFirebaseUpload](https://github.com/ayush-rathore/react-hooks/blob/main/src/useFirebaseUpload.js) - Custom hook to upload files to Firebase Storage

## Usage/Examples

```javascript
import useRecord from "./src/useRecord";
import useFirebaseUpload from "./src/useFirebaseUpload";

// Optional
import { TouchableOpacity } from "react-native";
import { Feather } from "@expo/vector-icons";

// Call the function upload with arg URL
async function upload(URL) {
	await useFirebaseUpload(URL).then((res) => {
		console.log("Download URL: ", res);
		return res;
	});
}

function App() {
	const { startRecording, stopRecording, recording, recordingURL, duration } =
		useRecord();

	return recording ? (
		<TouchableOpacity onPress={stopRecording}>
			<View>
				<Feather name="mic-off" size={18} color="#000" />
			</View>
		</TouchableOpacity>
	) : (
		<TouchableOpacity onPress={startRecording}>
			<View>
				<Feather name="mic" size={18} color="#000" />
			</View>
		</TouchableOpacity>
	);
}
```

## Support

For support, email heyfreaker@gmail.com
