<?xml version="1.0" encoding="UTF-8"?>
<Screen1
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:versionCode="1"
    android:versionName="1.0"
    android:theme="@android:style/Theme.Light">

    <!-- User Authentication -->
    <UserAuthentication>
        <Block type="Check_User_Status" />
        <Block type="VIP_Check">
            <Property name="vipStatus">false</Property>
        </Block>
    </UserAuthentication>

    <!-- Firebase Admin Control -->
    <FirebaseControl>
        <Block type="Firebase_Initialize">
            <Property name="databaseURL">https://your-app.firebaseio.com/</Property>
        </Block>
        <Block type="Firebase_GetValue">
            <Property name="path">/admin/ad_control</Property>
            <Property name="storeIn">adControl</Property>
        </Block>
        <Block type="If">
            <Condition>adControl == "on"</Condition>
            <Then>
                <Block type="Enable_Ads" />
            </Then>
            <Else>
                <Block type="Disable_Ads" />
            </Else>
        </Block>
    </FirebaseControl>

    <!-- WebView to Load Website Inside App -->
    <WebView
        android:id="@+id/webView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:url="https://yourwebsite.com" />

    <!-- Adsterra Direct Link Integration -->
    <WebView>
        <Block type="Load_URL">
            <Property name="url">https://www.adsterradirectlink.com/yourdirectlink</Property>
        </Block>
    </WebView>

    <!-- AdMob Banner Ad -->
    <com.google.android.gms.ads.AdView
        android:id="@+id/adView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:adSize="BANNER"
        android:adUnitId="ca-app-pub-XXXXXXXXXXXXXXXX/XXXXXXXXXX" />

    <!-- AdMob Interstitial Ad -->
    <com.google.android.gms.ads.InterstitialAd
        android:id="@+id/interstitialAd"
        android:adUnitId="ca-app-pub-XXXXXXXXXXXXXXXX/XXXXXXXXXX" />

    <!-- Ad Timing Control -->
    <AdTiming>
        <Block type="Set_Ad_Interval">
            <Property name="interval">30</Property>
        </Block>
    </AdTiming>

    <!-- Kodular Blocks to Load Ad -->
    <KodularBlocks>
        <Block type="AdMob_Load_Banner">
            <Property name="adUnitId">ca-app-pub-XXXXXXXXXXXXXXXX/XXXXXXXXXX</Property>
        </Block>
        <Block type="AdMob_Load_Interstitial">
            <Property name="adUnitId">ca-app-pub-XXXXXXXXXXXXXXXX/XXXXXXXXXX</Property>
        </Block>
        <Block type="Check_VPN_Status">
            <Property name="blockIfVPN">true</Property>
        </Block>
    </KodularBlocks>

</Screen1>
# kodular.aia
