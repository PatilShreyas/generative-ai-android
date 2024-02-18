# Google Generative AI SDK for Kotlin Multiplatform

The Google Generative AI client SDK for Kotlin Multiplatform enables developers to use Google's 
state-of-the-art generative AI models (like Gemini) to build AI-powered features and applications. 
This SDK supports use cases like:
- Generate text from text-only input
- Generate text from text-and-images input (multimodal)
- Build multi-turn conversations (chat)

For example, with just a few lines of code, you can access Gemini's multimodal capabilities to 
generate text from text-and-image input:

```kotlin
val generativeModel = GenerativeModel(
    modelName = "gemini-1.0-pro-vision-latest",
    apiKey = "YOUR_API_KEY"
)

val cookieImageData: ByteArray = // ...
val inputContent = content {
  image(PlatformImage(cookieImageData))
  text("Does this look store-bought or homemade?")
}

val response = generativeModel.generateContent(inputContent)
print(response.text)
```

Support following Kotlin Multiplatform targets:
- [x] Android
- [x] iOS
- [x] JVM
- [x] JS
- [x] Wasm (_Use this [version](https://github.com/PatilShreyas/generative-ai-kmp/releases/tag/v0.1.2-0.0.1-wasm)_)

## Installation and usage

Add the following dependency to your Kotlin Multiplatform project for `commonMain`:

```kotlin
commonMain.dependencies {
    implementation("dev.shreyaspatil.generativeai:generativeai-google:<version>")
}
```

Check for latest version in the [releases](https://github.com/PatilShreyas/generative-ai-kmp/releases) 
<a href="https://search.maven.org/search?q=g:dev.shreyaspatil.generativeai"><img src="https://img.shields.io/maven-central/v/dev.shreyaspatil.generativeai/generativeai-google?label=Maven%20Central&logo=kotlin&style=flat-square"/></a>

For detailed instructions, you can find a [quickstart](https://ai.google.dev/tutorials/android_quickstart) 
for the Google AI client SDK for Android (_Since this is a Fork of the original project by Google_).

This quickstart describes how to add your API key and the SDK's dependency to your app, 
initialize the model, and then call the API to access the model. It also describes some additional 
use cases and features, like streaming, counting tokens, and controlling responses.

## Documentation

You can use the APIs mentioned in the [API Reference](https://ai.google.dev/tutorials/android_quickstart)
by official library.

From the official library, there are two major changes:
- Package `com.google` is mapped to `dev.shreyaspatil`.
- `Image(Bitmap)` was there for Android, instead `PlatformImage(ByteArray)` is used for KMP.

## Contributing

See [Contributing](https://github.com/patilshreyas/generative-ai-kmp/blob/main/CONTRIBUTING.md) for 
more information on contributing to the client SDK for multiplatform.

## Credits
Big thanks to Google for project [google/generative-ai-android](https://github.com/google/generative-ai-android).

## Fork License
Copyright for portions of the code are held by [Google] as part of project 
[google/generative-ai-android](https://github.com/google/generative-ai-android) under the 
Apache License, version 2.0. 
All other copyright for project generative-ai-multiplatform are held by [Google, 2023] under the 
Apache License, Version 2.0.

## License

The contents of this repository are licensed under the
[Apache License, version 2.0](http://www.apache.org/licenses/LICENSE-2.0).
