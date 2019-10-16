---
title: Microsoft Teams での Cloud Voice
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
search.appverid: MET150
description: Teams でクラウドボイスを展開するためのランディングページ
appliesto:
- Microsoft Teams
ms.openlocfilehash: f60159d2d9d65afd3837a0b48b82ac7e13b8e0df
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515834"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Microsoft Teams での Cloud Voice

[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 会議[&](deploy-meetings-microsoft-teams-landing-page.md)会議を展開したことがあるかもしれません。 これで、ユーザーにクラウド音声機能を追加する準備ができました。 

クラウドボイスは、構内交換機 (PBX) 機能と、公衆交換電話網 (PSTN) に接続するためのオプションを提供します。

この記事では、組織のプロファイルとビジネス要件に基づいて、既定のクラウドボイス設定を変更する必要があるかどうかを決定するのに役立ちます。次に、それぞれの変更について説明します。 設定を2つのグループに分割しました。これからは、主要[な変更](#core-deployment-decisions)の中心となります。 2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。

すべての組織が主要な決定を行い、その他の要件が組織にある場合は、次の資料を参照してください。



## <a name="learn-more-about-cloud-voice"></a>クラウドの音声について、詳細はこちらをご覧ください

次の記事では、Teams でのクラウド音声機能の展開と使用に関する詳細情報を提供しています。

- [Office 365 の電話システム](what-is-phone-system-in-office-365.md)
- [通話プランが設定された電話システム](calling-plan-landing-page.md)
- [電話システムのダイレクト ルーティング](direct-routing-landing-page.md)
- [Cloud Voice の展開](cloud-voice-deployment.md)
- [Microsoft テレフォニー ソリューション](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- 電話システムの詳細については、次のセッションをご覧ください。 [Microsoft Teams での電話システムの紹介](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

次に示す設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では、組織に適した動作にならない場合)。

## <a name="phone-system-office-365"></a>電話システム (Office 365)

電話システムは Microsoft の技術であり、Office 365 クラウドで、通話制御と構内交換 (PBX) 機能を有効にすることができます。 電話システムを使用すると、既存の構内交換機 (PBX) システムを、Office 365 から直接配布された機能セットに置き換えることができます。また、会社のクラウド生産性エクスペリエンスに密接に統合されています。


|確認事項|アクション |
|:------------|:-------|
|電話システムを実装するのは、どのようなユーザーの場所またはオフィスですか? |電話システムの詳細については、「 [Office 365 の電話システムとは](what-is-phone-system-in-office-365.md)」を参照してください。</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>公衆交換電話網 (PSTN) への接続

電話システムを公衆交換電話網 (PSTN) に接続して、ユーザーが世界中で電話をかけることができるようにするには、ビジネスニーズに応じたオプションがあります。  次のことを確認してください。


|確認事項|アクション |
| :------------|:-------|
| テレフォニーキャリアとして Microsoft 通話プランを使用しますか? | 詳細については、「[通話プランを使用した電話システム](calling-plan-landing-page.md)」を参照してください。|
| 自分のテレフォニーキャリアを使用する必要はありますか? | 詳細については、「[ダイレクトルーティングを使用した電話システム](direct-routing-landing-page.md)」を参照してください。
|||


## <a name="additional-deployment-decisions"></a>その他の展開に関する決定事項

組織のニーズと構成に基づいて、次の設定を変更することができます。

- ボイスメール
- 通話 id
- Microsoft からの電話番号
- ダイヤル プラン
- 通話キュー
- 自動応答

### <a name="voicemail"></a>ボイスメール

Azure ボイスメールサービスを利用したクラウドボイスメールは、Exchange メールボックスのみを対象としたボイスメールのデポジットをサポートしており、サードパーティのメールシステムをサポートしていません。 クラウドボイスメールには、既定で組織内のすべてのユーザーに対して有効になるボイスメールの議事録が含まれています。 ビジネスニーズによっては、特定のユーザーまたは組織全体のすべてのユーザーに対してボイスメールを無効にする必要がある場合があります。

|確認事項|アクション |
|:------------|:-------|
| クラウドボイスメールを有効にしますか? | ボイスメールのセットアップ手順については、「[クラウドボイスメール](set-up-phone-system-voicemail.md)をセットアップする」をご覧ください。
| 一部またはすべてのユーザーに対してボイスメールの書き起こしを有効にしますか? | ボイスメールのトランスクリプト機能をオフにするには、「[組織でボイスメールポリシーを設定](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)する」を参照してください。</li></ul>|
|||

### <a name="calling-identity"></a>通話 id

既定では、すべての発信通話で、割り当てられた電話番号が発信 id (発信者番号) として使用されます。 通話の受信者は、すぐに発信者を特定して、通話を承諾または拒否するかどうかを決定できます。

|確認事項|アクション |
|:------------|:-------|
|発信者番号認識を無効にするか、無効にしますか? | 発信者番号通知を変更またはブロックするには、「[ユーザーに発信者番号を設定](set-the-caller-id-for-a-user.md)する」を参照してください。 |
|||

### <a name="phone-numbers-from-microsoft"></a>Microsoft からの電話番号

Microsoft には、2種類の電話番号が用意されています。*加入者*(ユーザー) 番号は、組織内のユーザーに割り当てることができます。また、電話番号は有料またはフリーダイヤルのサービス*番号とし*て利用できます。加入者番号よりもキャパシティ。電話会議、自動応答、通話キューなどのサービスに割り当てることができます。

|確認事項|アクション |
| :------------|:-------|
| Microsoft からの新しい電話番号が必要なユーザーの場所 | 電話番号を取得する方法については、「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」および「[ユーザーの電話番号を取得](getting-phone-numbers-for-your-users.md)する」を参照してください。 
| 必要な電話番号の種類 (加入者またはサービス) | 必要な電話番号の種類を選択するには、「[通話プラン用に使用される電話番号が異なる](different-kinds-of-phone-numbers-used-for-calling-plans.md)」を参照してください。
既存の電話番号を Office 365 に移植するにはどうすればよいですか?|詳細については、「 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)」を参照してください。
|||

### <a name="dial-plans"></a>ダイヤル プラン

Office 365 の電話システム機能のダイヤルプランは、ダイヤルされた電話番号を別の形式 (通常は164形式) に変換する正規化ルールのセットです。これは、通話承認と通話ルーティングに適しています。

ダイヤル プランの詳細については、「[ダイヤル プランについて](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)」を参照してください。

|確認事項|アクション |
|:------------|:-------|
| 組織はダイヤル プランのカスタマイズを必要としているか? | カスタムダイヤルプランが必要かどうかを判断する方法については、「[テナントダイヤルプランの計画](what-are-dial-plans.md#planning-for-tenant-dial-plans)」を参照してください。|
どのユーザーがダイヤル プランのカスタマイズを要求していて、どのテナント ダイヤル プランを各ユーザーに割り当てる必要があるか? | PowerShell のカスタマイズされたダイヤルプランにユーザーを追加する方法については、「[ダイヤルプランを作成して管理](create-and-manage-dial-plans.md)する」を参照してください。 |
|||

### <a name="call-queues"></a>通話キュー

クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。 


|確認事項|アクション |
|:------------|:-------|
| 組織には通話キューが必要ですか? | 詳細については、「[クラウドの通話キューを作成する](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」と「[電話システム](setting-up-your-phone-system.md)をセットアップする」を参照してください。 |

### <a name="auto-attendants"></a>自動応答

クラウド自動応答を使用すると、外部および内部の発信者がメニューシステムを通じて組織内の会社のユーザーや部署に通話を発信したり、転送したりできるように、組織のメニューシステムを作成することができます。

|確認事項|アクション |
|:------------|:-------|
| 組織に自動応答が必要ですか? | 詳細については、「[クラウド自動応答](what-are-phone-system-auto-attendants.md)と[クラウド自動応答のセットアップ](create-a-phone-system-auto-attendant.md)とは」を参照してください。 |

### <a name="devices"></a>デバイス

サポートされているデバイスの詳細については、次を参照してください。

- [Microsoft Teams でのデバイスを管理する](device-management.md)
- [IP 電話](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB オーディオ デバイスおよびビデオ デバイス](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [デバイスのインテリジェントな通信](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


