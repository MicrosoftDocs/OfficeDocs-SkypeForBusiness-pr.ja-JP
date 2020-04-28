---
title: Microsoft Teams でのクラウド ボイス
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: クラウドボイス機能についての詳細を確認して、必要な展開の意思決定について理解してください。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20a46a82c336396ccb71587db71515b699a9056e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905909"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Microsoft Teams でのクラウド ボイス


            [使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 [会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)も展開しました。 これで、ユーザーに対してクラウド ボイス機能を追加する準備が整いました。 

クラウド ボイスには、構内交換機 (PBX) 機能が用意されています。公衆交換電話網 (PSTN) に接続するためのオプションもあります。

この記事では、自分の組織のプロファイルとビジネスの要件に基づいて、既定のクラウド ボイスの設定に変更が必要かどうかを判断する際のガイダンスを示し、それぞれの変更の手順を説明します。 設定については 2 つのグループに分け、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分から説明します。 2 番目のグループには、組織のニーズ応じた構成する可能性のある[追加の設定](#additional-deployment-decisions)が含まれています。

中心的な部分についてはすべての組織が実行し、残りの内容は、組織に追加の要件がある場合に確認するようお勧めします。



## <a name="learn-more-about-cloud-voice"></a>クラウド ボイスの詳細

Microsoft Teams でのクラウド ボイスの展開と使用の詳細については、次の記事をご覧ください。

- [Office 365 の電話システム](what-is-phone-system-in-office-365.md)
- [通話プランが設定された電話システム](calling-plan-landing-page.md)
- [電話システムのダイレクト ルーティング](direct-routing-landing-page.md)
- [クラウド ボイスの展開](cloud-voice-deployment.md)
- [Microsoft テレフォニー ソリューション](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- 電話システムの詳細については、「[Microsoft Teams での電話システムの概要](https://aka.ms/teams-phone-system)」のセッションを視聴してください。


## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

次に示す設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では、組織に適した動作にならない場合)。

## <a name="phone-system-office-365"></a>電話システム (Office 365)

電話システムは、Office 365 クラウドで通話コントロールと構内交換機 (PBX) 機能を利用できるようにする Microsoft の技術です。 電話システムを使用すると、既存の構内交換機 (PBX) システムを、Office 365 から直接配布された機能セットに置き換えることができます。また、会社のクラウド生産性エクスペリエンスに密接に統合されています。


|確認事項|Action |
|:------------|:-------|
|どんなユーザーの場所、またはオフィスに電話システムを実装しますか? |電話システムの詳細については、「[Office 365 の電話システムとは](what-is-phone-system-in-office-365.md)」を参照してください。</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>公衆交換電話網 (PSTN) への接続

電話システムを公衆交換電話網 (PSTN) へ接続してユーザーが世界中に電話をかけることができるようにする場合、ビジネス ニーズに応じた選択肢があります。  次の点について確認してください。


|確認事項|Action |
| :------------|:-------|
| Microsoft 通話プランをテレフォニー通信事業者として使用しますか? | 詳細については、「[通話プランが設定された電話システム](calling-plan-landing-page.md)」を参照してください。|
| 自分のテレフォニー通信事業者を使用する必要がありますか? | 詳細については、「[直接ルーティングを行う電話システム](direct-routing-landing-page.md)」を参照してください。
|||


## <a name="additional-deployment-decisions"></a>その他の展開に関する決定事項

次の設定は、組織のニーズと構成に基づいて変更できます。

- ボイスメール
- 通話 ID
- Microsoft からの電話番号
- ダイヤル プラン
- 通話キュー
- 自動応答

### <a name="voicemail"></a>ボイスメール

Azure ボイスメールサービスを利用したクラウドボイスメールは、Exchange メールボックスのみを対象としたボイスメールのデポジットをサポートしており、サードパーティのメールシステムをサポートしていません。 クラウド ボイスメールでは、組織内のすべてのユーザーに対してボイスメールの文字起こしが既定で有効になっています。 会社のニーズに応じて、特定のユーザーまたは組織全体の全ユーザーに対してボイスメールの文字起こしを無効にすることができます。

|確認事項|Action |
|:------------|:-------|
| クラウド ボイスメールを有効にしますか? | ボイスメールのセットアップ手順については、「[クラウド ボイスメールのセットアップ](set-up-phone-system-voicemail.md)」を参照してください。
| 一部またはすべてのユーザーのボイスメールの文字起こしを有効にしますか? | ボイスメールの文字起こしをオフにする方法については、「[組織のボイスメール ポリシーの設定](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)」を参照してください。</li></ul>|
|||

### <a name="calling-identity"></a>通話 ID

既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。 通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。

|確認事項|Action |
|:------------|:-------|
|発信者 ID のマスクや無効化を行いますか? | 発信者 ID を変更またはブロックするには、「[ユーザーの発信者 ID を設定する](set-the-caller-id-for-a-user.md)」を参照してください。 |
|||

### <a name="phone-numbers-from-microsoft"></a>Microsoft からの電話番号

Microsoft では、2 種類の電話番号が用意されています。*サブスクライバー* (ユーザー) 番号は、組織内のユーザーに割り当てることができます。*サービス*番号は、有料および無料のサービス番号として使うことができ、サブスクライバー番号よりも大きな同時呼び出しの容量があり、電話会議、自動応答、通話キューなどのサービスを割り当てることができます。

|確認事項|Action |
| :------------|:-------|
| Microsoft からの新しい電話番号が必要なのはどのユーザー ロケーションですか? | 電話番号を取得する方法については、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」および「[ユーザー用の電話番号を取得する](getting-phone-numbers-for-your-users.md)」を参照してください。 
| どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)? | 必要な電話番号の種類を選択するには、「[通話プランで使用される電話番号の種類](different-kinds-of-phone-numbers-used-for-calling-plans.md)」を参照してください。
どんな方法で既存の電話番号を Teams に移植しますか?|詳細については、「[Microsoft Teams に電話番号を転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」を参照してください。
|||

### <a name="dial-plans"></a>ダイヤル プラン

Office 365 の電話システム機能であるダイヤル プランは、通話の認証およびルーティングの目的で、ダイヤルされた電話番号を代替形式 (通常は E.164 形式) に変換する正規化ルールです。

ダイヤル プランの詳細については、「[ダイヤル プランについて](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)」を参照してください。

|確認事項|アクション |
|:------------|:-------|
| 組織はダイヤル プランのカスタマイズを必要としているか? | カスタムのダイヤル プランが必要かどうかを判断するには、「[テナント ダイヤル プランの計画](what-are-dial-plans.md#planning-for-tenant-dial-plans)」を参照してください。|
どのユーザーがダイヤル プランのカスタマイズを要求していて、どのテナント ダイヤル プランを各ユーザーに割り当てる必要がありますか? | PowerShell で、カスタマイズしたダイヤル プランにユーザーを追加するには、「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」を参照してください。 |
|||

### <a name="call-queues"></a>通話キュー

クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。 


|確認事項|Action |
|:------------|:-------|
| 組織で通話キューは必要ですか? | 詳細については、「[クラウドの通話キューを作成する](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」および「[電話システムをセットアップする](setting-up-your-phone-system.md)」を参照してください。 |

### <a name="auto-attendants"></a>自動応答

クラウド自動応答を使用して、組織のメニュー システムを作成できます。外部および内部の発信者はこのメニュー システムを介して組織内の企業ユーザーまたは部門を特定し、通話の発信および転送を行うことができます。

|確認事項|Action |
|:------------|:-------|
| 組織で自動応答は必要ですか? | 詳細については、「[クラウド自動応答とは](what-are-phone-system-auto-attendants.md)」および「[クラウドの自動応答をセットアップする](create-a-phone-system-auto-attendant.md)」を参照してください。 |

### <a name="devices"></a>デバイス

サポートされているデバイスの詳細については、以下を参照してください。

- [Microsoft Teams でのデバイスの管理](device-management.md)
- [IP 電話](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB オーディオ デバイスおよびビデオ デバイス](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [デバイスのインテリジェント コミュニケーション](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


