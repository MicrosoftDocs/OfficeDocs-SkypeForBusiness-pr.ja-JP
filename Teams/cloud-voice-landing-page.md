---
title: Microsoft Teams での Cloud Voice
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: チームでクラウドの音声を展開するためのランディング ・ ページ
appliesto:
- Microsoft Teams
ms.openlocfilehash: abc8d3e552820ee93b5ccd1fc968e914ac5287ba
ms.sourcegitcommit: 4e750efd107dfc9bfd8b09d64abd40e0e27734de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2019
ms.locfileid: "30948378"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Microsoft Teams での Cloud Voice

[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 かもしれません[& 会議の会議](deploy-meetings-microsoft-teams-landing-page.md)を導入しました。 ユーザーのクラウドの音声機能を追加する準備が整いました。 

クラウドの音声は、プライベート構内交換機 (PBX) の機能が用意されています、、公衆交換電話網 (PSTN) を接続するためのオプションです。

この資料では、その手順を説明する各変更し、組織のプロファイルとビジネス要件に基づいて、既定のクラウド音声設定のいずれかを変更する必要があるかどうかを決定できます。 中核となる一連の[変更](#core-deployment-decisions)、2 つのグループの設定を分割しました。 2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。

すべての組織が主要な意思決定を進めるし、組織に追加の要件がある場合が、以下の内容を確認しをお勧めします。



## <a name="learn-more-about-cloud-voice"></a>クラウドの声の詳細を表示します

次の記事では、展開して、クラウドの音声機能を使用して、チームでの詳細についてを提供します。

- [Office 365 の電話システム](what-is-phone-system-in-office-365.md)
- [通話プランと電話システム](calling-plan-landing-page.md)
- [電話システムのダイレクト ルーティング](direct-routing-landing-page.md)
- [Cloud Voice の展開](cloud-voice-deployment.md)
- [Microsoft テレフォニー ソリューション](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- 電話システムの詳細については、次のセッションを監視する:[マイクロソフトのチームでの電話システムの概要](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

次に示す設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では、組織に適した動作にならない場合)。

## <a name="phone-system-office-365"></a>電話システム (Office 365)

電話システムは、通話の制御、Office 365 のクラウド内のプライベート構内交換機 (PBX) 機能を有効にする Microsoft のテクノロジです。 電話システムを使用すると、Office 365 から直接配信し、企業のクラウドの生産性の経験と密接に統合の機能のセットを使用して、既存のプライベート構内交換機 (PBX) システムを置き換えることができます。


|確認事項|アクション |
|:------------|:-------|
|電話システムはどのユーザーの所在地、またはオフィスで実装されますか。 |電話システムの詳細については、 [Office 365 の電話システムと](what-is-phone-system-in-office-365.md)を参照してください。</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>一般への接続は、電話網 (PSTN) を切り替える

世界中のユーザーが電話をかけることができますされるように、公衆交換電話網 (PSTN) 電話システムを接続するには、ビジネス ・ ニーズに基づいてのオプションがあります。  以下を確認してください。


|確認事項|アクション |
| :------------|:-------|
| [テレフォニーのキャリアとして Microsoft の計画を呼び出すを使用するか。 | 詳細については、[計画を呼び出すと、電話システム](calling-plan-landing-page.md)を参照してください。|
| 自分のテレフォニーのキャリアを使用する必要がありますか。 | 詳細については、[直接ルーティングの電話システム](direct-routing-landing-page.md)を参照してください。
|||


## <a name="additional-deployment-decisions"></a>その他の展開に関する決定事項

、次の設定を変更することも、組織のニーズに基づいて構成します。

- ボイスメール
- 識別情報を呼び出す
- マイクロソフトの電話番号
- ダイヤル プラン
- 通話キュー
- 自動応答

### <a name="voicemail"></a>ボイスメール

電源は、Azure のボイスメール サービスが、クラウドのボイスメール ボイスメール出金のみの Exchange メールボックスをサポートしている、サード ・ パーティ製の電子メール システムをサポートしていません クラウドのボイス メールには、組織内のすべてのユーザーに対して既定で有効には、ボイスメールの議事録が含まれています。 ビジネス ニーズは、特定のユーザーまたは組織全体のすべてのユーザーのボイスメールの議事録作成を無効にする必要があります。

|確認事項|アクション |
|:------------|:-------|
| クラウドのボイスメールを有効にするか。 | ボイスメールの設定手順は、「[クラウドのボイスメールを設定](set-up-phone-system-voicemail.md)」を参照してください。
| ボイスメールの議事録の一部またはすべてのユーザーを有効にするか。 | ボイスメールの議事録作成を無効にするには、[組織内のボイス メール ポリシーの設定](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)を参照してください。</li></ul>|
|||

### <a name="calling-identity"></a>識別情報を呼び出す

既定では、すべての発信呼び出しは、呼び出し元の id (呼び出し元 ID) として割り当てられた電話番号を使用します。 呼び出しの受信者は、呼び出し元を識別する迅速かつ呼び出しを承認または拒否かどうかを決定します。

|確認事項|アクション |
|:------------|:-------|
|マスクしたり、発信者番号通知を無効にするか。 | 呼び出し元 ID のブロックを変更または、[ユーザーの発信者番号の設定](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)を参照してください。 |
|||

### <a name="phone-numbers-from-microsoft"></a>マイクロソフトの電話番号

マイクロソフトでは、2 種類の利用可能な電話番号:*サブスクライバー* (ユーザー) の番号は、組織内のユーザーに割り当てることができる、および*サービス*の番号、有料電話番号と無料サービスの番号より高い同時実行の呼び出しとして利用可能加入者番号よりも容量と、オーディオ会議、自動応答、またはキューの呼び出しなどのサービスに割り当てることができます。

|確認事項|アクション |
| :------------|:-------|
| どのユーザーの場所には、マイクロソフトからの新しい電話番号が必要ですか。 | 電話番号の取得方法の詳細については、[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)し[、ユーザーの電話番号の取得](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)を参照してください。 
| 電話番号 (サブスクライバーまたはサービス) の種類が必要ですか。 | 必要がある電話番号の種類を選択するために、[さまざまな種類](different-kinds-of-phone-numbers-used-for-calling-plans.md)を参照してください。
Office 365 を既存の電話番号をポートするには?|詳細については、 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。
|||

### <a name="dial-plans"></a>ダイヤル プラン

Office 365 の電話システムの機能で、ダイヤル プランは、承認と通話のルーティングの他の形式 (通常は E.164 形式) に電話番号をダイヤルに変換する正規化ルールのセットです。

ダイヤル プランの詳細については、「[ダイヤル プランについて](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)」を参照してください。

|確認事項|アクション |
|:------------|:-------|
| 組織はダイヤル プランのカスタマイズを必要としているか? | カスタムのダイヤル プランを使用する場合を判断するためには、[テナントを計画するダイヤル プラン](what-are-dial-plans.md#planning-for-tenant-dial-plans)を参照してください。|
どのユーザーがダイヤル プランのカスタマイズを要求していて、どのテナント ダイヤル プランを各ユーザーに割り当てる必要があるか? | PowerShell でカスタマイズされたダイヤル プランにユーザーを追加するを参照してください[を作成するダイヤル プランの管理と](create-and-manage-dial-plans.md)。 |
|||

### <a name="call-queues"></a>通話キュー

電話システム キューには、保留中の呼び出しを自動的に配置する機能などを検索する人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントの機能の電話番号への呼び出し際に使用するあいさつ文が含まれています。呼び出しが保留中の音楽をリッスンしています。 組織の 1 つまたは複数の呼び出しキューを作成します。 


|確認事項|アクション |
|:------------|:-------|
| 自分の所属組織はキューを呼び出して必要がありますでしょうか。 | 詳細については、[電話システムの呼び出しキューを作成](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)し[、電話システムの設定](setting-up-your-phone-system.md)を参照してください。 |

### <a name="auto-attendants"></a>自動応答

電話システムの自動応答を使用して、内部および外部の呼び出し元では、組織のメニュー システムを作成することは、メニューを探し、配置、ユーザーの会社または組織内の部門への呼び出しを転送するシステムを移動します。

|確認事項|アクション |
|:------------|:-------|
| 自分の所属組織は自動応答を必要ですか。 | 詳細については、[自動応答の電話システムとは](what-are-phone-system-auto-attendants.md)[電話システムの自動応答の設定](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照してください。 |

### <a name="devices"></a>デバイス

サポートされているデバイスの詳細については、以下を参照してください。

- [Microsoft Teams でのデバイスを管理する](device-management.md)
- [IP 電話](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB オーディオ デバイスおよびビデオ デバイス](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [デバイスのインテリジェント通信](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


