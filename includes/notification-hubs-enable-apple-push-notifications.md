---
title: インクルード ファイル
description: インクルード ファイル
services: notification-hubs
author: spelluru
ms.service: notification-hubs
ms.topic: include
ms.date: 04/11/2018
ms.author: spelluru
ms.custom: include file
ms.openlocfilehash: 10ccb80dd74606d2ad40ab5d7993aed8cd71725e
ms.sourcegitcommit: 65b399eb756acde21e4da85862d92d98bf9eba86
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2018
ms.locfileid: "36329673"
---
## <a name="generate-the-certificate-signing-request-file"></a>証明書の署名要求ファイルを生成する
Apple Push Notification Service (APNS) では、証明書を使用してプッシュ通知を認証します。 次の手順に従って、通知を送受信するために必要なプッシュ証明書を作成します。 これらの概念の詳細については、[Apple Push Notification Service](http://go.microsoft.com/fwlink/p/?LinkId=272584) の公式ドキュメントを参照してください。

Apple が署名済みのプッシュ証明書を生成するために使用する、証明書署名要求 (CSR: Certificate Signing Request) ファイルを生成します。

1. Mac で、キーチェーン アクセス ツールを実行します。 これは、Launchpad の **[Utilities]** フォルダーまたは **[Other]** フォルダーから開くことができます。
2. **[Keychain Access]** をクリックし、**[Certificate Assistant]** を展開して、**[Request a Certificate from a Certificate Authority]** をクリックします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-request-cert-from-ca.png)
3. **[User Email Address]** と **[Common Name]** を選択し、**[Saved to disk]** が選択されていることを確認して、**[Continue]** をクリックします。 必要ではないため、" **CA 電子メール アドレス** " フィールドを空白のままにします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-csr-info.png)
4. **[Save As]** に証明書署名要求 (CSR) ファイルの名前を入力し、**[Where]** で保存場所を選択して **[Save]** をクリックします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-save-csr.png)
   
      このアクションで、指定選択した場所に CSR ファイルが保存されます。既定の場所は [Desktop] です。 ファイル用に選択した場所を忘れないでください。

次に、アプリケーションを Apple に登録し、プッシュ通知を有効にし、エクスポートした CSR をアップロードしてプッシュ通知を作成します。

## <a name="register-your-app-for-push-notifications"></a>アプリケーションをプッシュ通知に登録する
iOS アプリケーションにプッシュ通知を送信できるようにするには、アプリケーションを Apple に登録し、プッシュ通知にも登録する必要があります。  

1. アプリをまだ登録していない場合は、Apple Developer センターで <a href="http://go.microsoft.com/fwlink/p/?LinkId=272456" target="_blank">iOS Provisioning Portal</a> に移動し、Apple ID でサインインして、**[Identifiers]** をクリックし、**[App IDs]** をクリックします。最後に、**+** 記号をクリックして新しいアプリを登録します。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-ios-appids.png)
      
2. 新しいアプリの次の 3 つのフィールドを更新し、 **[Continue]** をクリックします。
   
   * **Name**: **[App ID Description]** セクションの **[Name]** フィールドに、アプリのわかりやすい名前を入力します。
   * **Bundle Identifier**: **[Explicit App ID]** セクションに、[アプリ ディストリビューション ガイド](https://developer.apple.com/library/mac/documentation/IDEs/Conceptual/AppDistributionGuide/ConfiguringYourApp/ConfiguringYourApp.html#//apple_ref/doc/uid/TP40012582-CH28-SW8)で説明したように `<Organization Identifier>.<Product Name>` の形式で**バンドル ID** を入力します。 使用する "*組織 ID*" と "*製品名*" は XCode プロジェクトを作成する際に使用する組織 ID と製品名に一致させる必要があります。 以下のスクリーンショットでは、組織 ID として *NotificationHubs*、製品名として *GetStarted* を使用しています。 この値と、XCode プロジェクトで使用する値が一致していることを確認することで、XCode で正しい発行プロファイルが使用できるようになります。 
   * **[Push Notifications (プッシュ通知)]**: **[App Services (アプリ サービス)]** セクションの **[Push Notifications (プッシュ通知)]** オプションを選択します。
     
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-new-appid-info.png)
     
      このアクションで、アプリケーションID が生成され、情報の確認が求められます。 **[Register (登録)]** をクリックして新しいアプリケーション ID を確定します。
     
      **[Register]** をクリックすると、以下の図にあるような **[Registration complete]** 画面が表示されます。 **[Done]** をクリックします。
      
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-appid-registration-complete.png)


1. Developer センターで、アプリケーション ID の一覧から作成したアプリケーション ID を見つけ、その行をクリックします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-ios-appids2.png)
   
      アプリ ID をクリックすると、アプリの詳細が表示されます。 画面の下部にある **[Edit]** をクリックします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-edit-appid.png)
      
2. 画面の下部までスクロールし、**[Development Push SSL Certificate]** セクションの **[Create Certificate]** ボタンをクリックします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-appid-create-cert.png)
   
      [Add iOS Certificate] アシスタントが表示されます。
   
   > [!NOTE]
   > このチュートリアルでは開発証明書を使用します。 運用証明書の場合も同じ処理を行います。 通知の送信と同じ証明書の種類を使用するようにします。
   > 
   > 
3. **[Choose File]** をクリックして、最初の作業で CSR ファイルを保存した場所に移動し、**[Generate]** をクリックします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-appid-cert-choose-csr.png)
4. ポータルで証明書が作成されたら **[Download]** ボタンをクリックし、**[Done]** をクリックします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-appid-download-cert.png)
   
      証明書がダウンロードされ、コンピューターの Downloads フォルダーに保存されます。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-cert-downloaded.png)
   
   > [!NOTE]
   > 既定では、ダウンロードした開発証明書ファイルの名前は **aps_development.cer** になっています。
   > 
   > 
5. ダウンロードしたプッシュ証明書 **aps_development.cer** をダブルクリックします。
   
      このアクションで、以下の図のように、新しい証明書がキーチェーンにインストールされます:
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-cert-in-keychain.png)
   
   > [!NOTE]
   > 証明書の名前は異なることがありますが、名前の前に **Apple Development iOS Push Services**が付けられます。   
6. Keychain Access の **[Certificates]** カテゴリで、作成した新しいプッシュ証明書を右クリックします。 **[Export]** をクリックし、ファイルに名前を付けて、**.p12** 形式を選択します。次に、**[Save]** をクリックします。
   
    ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-export-cert-p12.png)
   
    エクスポートした .p12 証明書のファイル名と場所を書き留めます。 APNS での認証には、これが使用されます。
   
   > [!NOTE]
   > このチュートリアルでは QuickStart.p12 ファイルを作成します。 ファイル名と場所は同じである必要はありません。
   
## <a name="create-a-provisioning-profile-for-the-app"></a>アプリケーションのプロビジョニング プロファイルを作成する
1. <a href="http://go.microsoft.com/fwlink/p/?LinkId=272456" target="_blank">iOS Provisioning Portal</a> に戻って **[Provisioning Profiles]** を選択し、**[All]** を選択してから **+** ボタンをクリックして、新しいプロファイルを作成します。 これにより、**Add iOS Provisiong Profile** ウィザードが表示されます
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-new-provisioning-profile.png)
2. **[Development (開発)]** でプロビジョニング プロファイルの種類として **[iOS App Development (iOS アプリ開発)]** を選択し、**[Continue (続行)]** をクリックします。 
3. 次に、**[App ID (アプリ ID)]** ドロップダウン リストから作成したアプリ ID を選択し、**[Continue (続行)]** をクリックします
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-select-appid-for-provisioning.png)
4. **[Select certificates]** 画面で、コードの署名に使用される通常の開発証明書を選択して、**[Continue]** をクリックします。 これは証明書であり、作成したプッシュ証明書ではありません。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-provisioning-select-cert.png)
5. 次に、テストに使用する**デバイス**を選択し、**[Continue]** をクリックします
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-provisioning-select-devices.png)
6. 最後に、**[Profile Name]** でプロファイルの名前を選択し、**[Generate]** をクリックします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-provisioning-name-profile.png)
7. 新しいプロビジョニング プロファイルが作成されたら、それをクリックしてダウンロードし、Xcode の開発用コンピューターにインストールします。 次に、 **[Done]** をクリックします。
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-provisioning-profile-ready.png)
