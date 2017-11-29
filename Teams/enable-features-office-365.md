---
title: "Office 365 を使用する組織で Microsoft Teams の機能を有効にする | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "テナント全体の設定、電子メール統合、アプリ、クラウド ストレージなど、Office 365 を使用する組織で有効に設定できるすべての Microsoft Teams 機能について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e2235756e77c3e27c1eeee9fd22decb5e0e4e062
ms.sourcegitcommit: db47b9f4955150859bc35ab9d078fa3ab66b5faa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2017
---
<a name="enable-microsoft-teams-features-in-your-office-365-organization"></a>Office 365 を使用する組織で Microsoft Teams の機能を有効にする
======================================================

Microsoft Teams には、テナント レベルで有効または無効にすることができる設定が複数あります。テナントで Teams を有効にすると、Teams が有効なすべてのユーザーにもテナント レベルの設定が継承されます。

Teams 内で Office 365 管理者が有効または無効にできる機能のリストを次に示します。

特に明記されていない場合を除き、オプションの規定値はオンです。

> [!NOTE]
> Office 365 管理者はいつでも Office 365 管理センターを介して Microsoft Teams をオフにすることができます。Teams をオフにした場合でも、Microsoft Teams の有効なライセンスを所有するユーザーには Teams アプリ タイルがそのまま表示され続けます。ユーザーからライセンスを削除する方法について詳しくは、「[Microsoft Teams へのユーザー アクセスを管理する](user-access.md)」をご覧ください。Teams を無効にすると、Teams クライアントからのアクセスが遮断されます。ただし、SharePoint や OneDrive を介したファイルなど、その他のクライアントやサービスから利用できるデータには継続的に利用できます。チームを明示的に削除しない限り、すべてのデータはそのまま残ります。

<a name="tenant-wide-settings"></a>テナント全体の設定 
---------------------

[**テナント全体の設定**] で、[全般]、[電子メール統合]、[アプリ]、[Custom cloud storage (カスタム クラウド ストレージ)] のオプションをオンまたはオフに切り替えられます。

### <a name="general"></a>全般

[全般] セクションでは組織の次の設定を構成できます。

> ![テナント全体にわたる設定の [全般] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **個人プロファイルに組織図を表示する:** この設定を有効にすると、組織図アイコンがユーザーの連絡先カードに表示されます。このアイコンをクリックすると、詳細な組織図が表示されます。

    ![ユーザーの連絡先カードの [組織図] アイコンのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![組織図のスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   **Microsoft Teams を所有していない受信者に対して Skype for Business を使用する:** この設定を有効にすると、Microsoft Teams のユーザーは組織内で Microsoft Teams が有効でないユーザーに対して Skype for Business 経由で連絡することができます。

-   **T-Bot がプロアクティブにヘルプ メッセージに送るのを許可する:** この設定を有効にすると、T-Bot はプライベート チャット セッションを開始し、Microsoft Teams の使用に関するガイドを提供します。

    ![Microsoft Teams インターフェイスの T-Bot セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>電子メール統合
-----------------

この機能をオンにすると、ユーザーはチャネル電子メール アドレスを使用して、Microsoft Teams のチャネルにメールを送信できるようなります。この操作は、ユーザーが所有するチームに属しているどのチャネルに対しても行えます。ユーザーのメールは、チーム メンバーに対して有効になっている追加のコネクタがあるチーム内の任意のチャネルにも送信できます。また、ユーザーにチャネル電子メール アドレスを作成する権限がない場合でも、権限のある他のユーザーがアドレスを作成すれば、そのアドレスに該当チャネルの \<その他アイコン\> メニューからアクセスできます。

[電子メール統合] セクションでは組織の次の設定を構成できます。

   ![テナント全体の設定の [電子メール統合] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image5.png)

-   **ユーザーがチャネルにメールを送信するのを許可する:** 有効にすると、メール フックが有効に設定されます。ユーザーは Microsoft Teams のチャネルの電子メール アドレス宛に電子メールを送信することでチャネルにメッセージを投稿できるようになります。

> チャネルの電子メール アドレスを見つけるには、チャネル名の隣にある [**その他のオプション**] をクリックしてから [**電子メール アドレスの取得**] を選択します。

-   **送信者の制限一覧:** 送信者のドメインをさらに制限して、SMTP ドメインのみが Microsoft Teams チャネルに電子メールを送信できるようにします。

<a name="apps"></a>アプリ
----

Microsoft Teams の [アプリ] は、チームが関心を持つツールとサービスをチャネルやチャットに統合するための優れたツールです。

[**アプリ**] セクションでは、組織の次の設定を構成できます。

![[アプリ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   **Microsoft Teams の外部アプリを許可する:** 有効にすると、ユーザーは Office 365 テナントで利用できるタブやボットを 追加することができます。
![[アプリ] セクションの外部アプリの許可コントロールのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

-   **外部アプリのサイドロードを許可する:** 有効にすると、ユーザーはカスタムのボットやタブをインストールして有効にすることができます。

<a name="custom-cloud-storage"></a>カスタム クラウド ストレージ
--------------------

現時点では、Microsoft Teams のクラウド ストレージ オプションには、Box、Dropbox、Google ドライブ、ShareFile があります。ユーザーは Microsoft Teams チャネルやチャットでクラウド ストレージ サービスを介してファイルをアップロード、共有できます。組織が使用するクラウド ストレージ プロバイダの横にあるトグル スイッチをクリックまたはタップします。

![[カスタム クラウド ストレージ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a>ライセンスでのユーザー設定
------------------------

[**ライセンスでのユーザー設定**] で、[チームとチャネル]、[通話と会議]、[メッセージング] でオプションをオンまたはオフにできます。

<a name="teams-and-channels"></a>チームとチャネル
------------------

チームは、業務遂行のために緊密に連携するグループ メンバーをまとめるように設計されています。チームは、プロジェクト ベースの作業向けで動的です (製品の立ち上げや、デジタル作戦指令室を作るなど)。また、組織の内部構造を反映して、随時変化していきます。

管理者として、ポータルの [グループ] ダッシュボードを使用して、チームの所有者とメンバーを管理することができます。[チームとチャネル] セクションで、[**Office 365 管理センターの [グループ] ダッシュボードを使用してチームを管理する**] のリンクをクリックしてください。

Microsoft Teams でチームを作成できる組織のユーザーを制御できます。Office 365 グループで定義した作成設定が Microsoft Teams にも適用されます。Office 365 グループの管理について詳しくは、「[Create Office 365 groups (Office 365 グループを作成する)](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f)」と「[Control who can create Office 365 Groups (Office 365 グループを作成できるユーザーを制御する)](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)」をご覧ください。

注意: [グループ] ダッシュボードでチームを作成することはできません。チームは、デスクトップ クライアントまたは Web アプリを使用して作成する必要があります。

既定では、どのユーザーもチームやグループを作成できます。ユーザーは、クライアント (デスクトップ クライアントまたは Web アプリ) の左側にある [チーム] を選択し、クライアントの下部のチーム リストの下にある [チームを作成] を選択して、チームを作成することができます。

現在、Office 365 テナントが所有できるチームの既定の最大数は 500,000 です。グローバル管理者はチームを無制限に作成できます。1 人のユーザーが作成できるチームの数は 250 です。チーム所有者は 2500 人のメンバーをチームに追加できます。

![[ライセンスでのユーザー設定] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

チャネルは、チームのサブカテゴリーです。チームの誰もがチャネルを追加したり、チャネル内の会話に参加できます。チャネルは、アクティビティや部署用に作成します。会話、ファイル、Wiki は、各チャネルに固有ですが、チーム内の全メンバーが見ることができます。

### <a name="calls-and-meetings"></a>通話と会議

[**通話と会話**] セクションでは、組織の次の設定を構成できます。

> ![[通話と会話] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   **Allow scheduling for private meetings (プライベート会議の予約を許可する):** 有効の場合、ユーザーはいずれのチャネルにもリストされていないプライベート会議を予約できます。

-   **Allow ad-hoc channel meetup (臨時のチャネル会合を許可する):**

-   **Allow scheduling for channel meetings (チャネル会議の予約を許可する):** 有効の場合、ユーザーは、すべてのチャネル メンバーが 1 回のクリックで簡単に参加できるチャネルの会議を予約することができます。

-   **会議のビデオを許可:** 会議でビデオの使用を許可するかどうかを指定します。

-   **会議の画面共有を許可:** 会議で画面共有を許可するかどうかを指定します。

-   **プライベート通話を許可:** 有効の場合、ユーザーはプライベート通話を行うことができます。

会議に参加できる人の最大数は 80人です。プライベート チャットでは、チャットの作成者を含め、最大 20 人です。

### <a name="messaging"></a>メッセージング 

[メッセージング] セクションでは組織の次の設定を構成できます。

![[メッセージング] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **Giphy を有効にして会話に gif を追加できるようにする:** 有効の場合、ユーザーは会話内でアニメーション画像を使用できます。

    -   **コンテンツ評価:** アニメーション画像がオンの場合は、コンテンツ評価を適用して、会話に表示できるアニメーション画像の種類を制限することができます。利用可能なコンテンツ評価は次のとおりです。

        -   制限なし

        -   中レベル (規定値)

        -   厳密

-   **Enable memes that users can edit and add to conversations (ミームを編集したり会話に追加できようにする):** 有効の場合、ユーザーはインターネット ミームを使用してユーモアのあるメッセージを投稿できます。

-   **Enable stickers that users can edit and add to conversations (ステッカーを編集したり会話に追加できようにする):** 有効の場合、ユーザーは編集可能なテキストを含む画像を投稿して、チャネル メンバーに注目させることができます。

-   **所有者がすべてのメッセージを削除することを許可する:** 有効の場合、チャネルの所有者はチャネルのすべてのメッセージを削除することができます。

-   **ユーザーが自分のメッセージを編集することを許可する:** 有効の場合、ユーザーは自分のメッセージを編集することができます。

-   **ユーザーが自分のメッセージを削除することを許可する:** 有効の場合、ユーザーは自分のメッセージを削除することができます。

-   **Allow users to chat privately (ユーザーがプライベートでチャットすることを許可する):** 有効の場合、ユーザーは、チーム メンバー全員ではなく、チャット内のユーザーにのみ表示されるプライベート チャットに参加できます。


| |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |判断ポイント         |組織で有効にする Microsoft Teams の設定を教えてください。         |
|![次のステップ アイコン。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |次のステップ        |[Microsoft Teams で役割と権限を割り当てる](assign-roles-permissions.md)の表における、これらの決定を文書化します。         |

