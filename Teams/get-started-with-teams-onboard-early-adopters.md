---
title: Microsoft Teams に早期導入者を参加させる
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 11/06/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: serdars
description: Microsoft Teams で作成した最初のチームおよびチャネルのセットに早期導入者を参加させる方法について説明します。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- seo-marvel-apr2020
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8062b0f1ada28289b2a6c62dc6a29c3b6cf1f751
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809497"
---
# <a name="onboard-early-adopters-to-microsoft-teams"></a>Microsoft Teams に早期導入者を参加させる

## <a name="invite-users-to-teams"></a>Teams にユーザーを招待する

作成したチームの名前と説明を記載した招待メールをユーザーに送信し、Teams での会話に参加するよう招待します。 Teams のクライアントの入手先と、トレーニングおよびサポートを受けられる場所がわかるように、次のリンクを必ず電子メールに含めます。
- [Teams の Web クライアント](https://teams.microsoft.com)
- [デスクトップとモバイル クライアントのダウンロード リンク](https://teams.microsoft.com/downloads)
- [Teams のトレーニング用ビデオ](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Teams のヘルプ ドキュメント](https://support.office.com/teams)

たとえば、"Get to know Teams" チームの場合は次のような電子メールを送信します。

   ```console
   Welcome to Microsoft Teams for <insert_company_name>. Teams is a chat-based workspace that brings together chat, files, people, and tools in one place. 

   We created a team called "Get to know Teams" to get you started. Use it to experiment, ask questions, and discover the possibilities of Teams. 

   To join, click <link to the team>.
   ```

ユーザーが初めて参加したときに、そのユーザーと会話を行います。 Teams で歓迎メッセージを投稿し、チャネルでチャットを開始します。 こうすることで口調を決定し、Teams への切り替えをユーザーに促します。 歓迎メッセージには電子メールで送信したリンクと同じものを含めて、ユーザーが Teams の入手場所を確認できるようにします。また、ユーザーがすぐに作業を開始できるようにするための、その他の有用な情報も含めます。 ユーザーが Teams のダウンロード、インストール、およびサインイン方法を確実に把握できるように、ユーザーに連絡を行います。これにより、ユーザーはチャットやファイルの共有、相互の共同作業を開始できます。  

## <a name="get-teams-clients"></a>Teams のクライアントを取得する
Teams には、デスクトップ用 (Windows および Mac)、Web 用、およびモバイル用 (iOS および Android) のクライアントがあります。 Teams を最大限活用するために、ユーザーはデスクトップとモバイル クライアントをインストールすることをお勧めします。 

参照先へジャンプ: [Windows 用 Teams](#teams-for-windows) | [Mac 用 Teams](#teams-for-mac) | [Web ブラウザー用 Teams](#web-client) | [iOS 用 Teams](#teams-for-ios) | [Android 用 Teams](#teams-for-android)

### <a name="desktop-client"></a>デスクトップ クライアント

Teams のデスクトップ クライアントは Windows ユーザーと Mac ユーザーに、すべてにおいて最高のエクスペリエンスを提供します。 詳細については、「[Teams のクライアントを取得する (デスクトップ クライアント)](https://docs.microsoft.com/MicrosoftTeams/get-clients#desktop-client)」および「[Microsoft Teams アプリのハードウェア要件](https://docs.microsoft.com/MicrosoftTeams/hardware-requirements-for-the-teams-app)」を参照してください。

> [!NOTE]
> 管理者は、Microsoft Endpoint Configuration Manager (Windows) や Jamf Pro (macOS) など、インストール ファイルを組織内のコンピューターに配布する方法を選択できます。

#### <a name="teams-for-windows"></a>Windows 用 Teams 
Windows デスクトップ クライアントをインストールする最も簡単な方法は、次のとおりです。

1. [https://teams.microsoft.com/downloads](https://teams.microsoft.com/downloads) から、Windows デスクトップ クライアントをダウンロードします。
2. インストーラーを実行します (管理者権限は不要)。 
3. インストールが完了したら、Teams を起動します。

> [!NOTE]
> その後、組織全体に Teams のより正式な大規模展開を検討する場合は、「[Teams Windows デスクトップ クライアント](https://aka.ms/teams-clients)」ビデオで計画と展開の方法を確認してください。 

#### <a name="teams-for-mac"></a>Mac 用 Teams 
Mac デスクトップ クライアントをインストールする最も簡単な方法は、次のとおりです。

1. [https://teams.microsoft.com/downloads](https://teams.microsoft.com/downloads) から、Mac デスクトップ クライアントをダウンロードします。
2. インストーラーを実行します (管理者権限が必要)。 
3. インストールが完了したら、Teams を起動します。

### <a name="web-client"></a>Web クライアント
Teams には、さまざまなブラウザーをサポートする、豊富な機能の Web クライアント ([https://teams.microsoft.com](https://teams.microsoft.com)) が用意されています。

[!INCLUDE [browser-support](includes/browser-support.md)]

### <a name="mobile-client"></a>モバイル クライアント

iOS および Android 用の Teams モバイル クライアントは、外出先でもユーザーとの接続性と生産性を維持します。 詳細については、「[Teams のクライアントを取得する (モバイル クライアント)](https://docs.microsoft.com/MicrosoftTeams/get-clients#mobile-clients)」を参照してください。

#### <a name="teams-for-ios"></a>iOS 用 Teams 

iOS 10.0 以降を実行しているユーザーは、Apple App Store から Teams モバイル アプリをダウンロードして、すぐに使用を開始できます。  

#### <a name="teams-for-android"></a>Android 用 Teams 
Android 4.4 以降を実行しているユーザーは、Google Play Store から Teams モバイル アプリをダウンロードして、すぐに使用を開始できます。  

## <a name="drive-initial-adoption"></a>初期導入を推進する

初期導入者に対して、積極的に Teams を使用し、新しい共同作業のエクスペリエンスを高めて、Teams のチャンピオンを育成するよう奨励することが重要です。 導入を促進するために、作成した "Get to know Teams" チームの "How do I" チャネルを使用して、ユーザーとガイダンスを共有することをお勧めします。 

組織への Teams の導入を推進するための詳細なガイダンスについては、「[Teams を導入する](adopt-microsoft-teams-landing-page.md)」を参照してください。

## <a name="next-steps"></a>次のステップ
「[使用状況とフィードバックを監視する](get-started-with-teams-monitor-usage-and-feedback.md)」に移動します。
