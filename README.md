# QattahPay Android SDK

[![](https://jitpack.io/v/QattahPay/qattahpay-android-sdk.svg)](https://jitpack.io/#QattahPay/qattahpay-android-sdk)


The QattahPay Android SDK provides a payment gateway integration with QattahPay, supporting both English and Arabic languages. The SDK offers a simplified checkout process and supports the latest version of Android.

## Installation

To use the QattahPay Android SDK in your project, add the following dependency to your app's build.gradle file:

```gradle
dependencies {
    implementation 'com.github.QattahPay:qattahpay-android-sdk:1.3'
}
```

## Usage

To use the QattahPay Android SDK, follow these steps:

1. Initialize the QattahPay SDK with your API key.
```kotlin
// build a new QattahPayBuilder and pass the activity and callbacks
        qattahPay = QattahPay
            .Builder()
            .activity(this)
            .callbacks(this)
            .apiKey(apiKey)
            .build()
```

2. Create a payment session with the required payment details by calling the `startNewQattahPaymentSession` method.
```kotlin
 // start a new payment session
            qattahPay.startNewQattahPaymentSession(orderId = "order-123123123", amount = 200.0, isSandbox = true)
```

3. Handle the payment result by implemnting the `QattahPayCallbacks`.
```kotlin
override fun onQattahPayStarted(qattahOrderId: String) {
        Toast.makeText(this, "Order ID: $qattahOrderId", Toast.LENGTH_SHORT).show()
    }

    override fun onQattahPaySucceed() {
        Toast.makeText(this, "Payment Success", Toast.LENGTH_SHORT).show()
    }

    override fun onQattahPayFailed(errorMessage: String) {
        Toast.makeText(this, "Payment Failed: $errorMessage", Toast.LENGTH_SHORT).show()
    }

    override fun onCancelled() {
        Toast.makeText(this, "Payment canceled", Toast.LENGTH_LONG).show()
    }
```

For more detailed information, refer to the QattahPay Android SDK documentation.

## Release Notes

### Version 0.1

- New payment gateway integration with QattahPay.
- Support for English and Arabic languages.
- Simplified checkout process.
- Support for the latest version of Android.

## License

The QattahPay Android SDK is licensed under the MIT License. See the LICENSE file for more information.
