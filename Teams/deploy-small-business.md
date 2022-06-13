---
title: 小規模ビジネスで Microsoft Teams を設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 小規模ビジネスで Teams を設定して、ユーザーがチャットやファイル共有を使用して共同作業したり、大小の会議を設定して参加したり、ビデオや音声で会話したりできるようにします。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3afa62cfaca28c0c428c15b44868e7237973955
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045446"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>小規模ビジネスで Microsoft Teams を設定する

Teams をカスタマイズする方法はたくさんあります。 以下のセクションでは、**チャット、チーム、チャネル**、**ミーティングと会議**、および **音声ソリューション** に関する Teams の各ワークロードを設定する方法を説明します。 各ワークロードを設定する順序に決まりはありません。 最初にチャット、チーム、チャネルのワークロードを設定することをお勧めしますが、ミーティングと会議から始めることも、クラウド ボイスから始めることもできます。 選択は自由です。

> [!NOTE]
> まだ行っていない場合は、パイロットから Teams の展開を開始することを強くお勧めします。パイロットにより、計画と最終的な展開の前に、あなたや早期採用者が Teams とその機能に精通することができます。パイロットを開始する方法の詳細については、「[Microsoft Teams を開始する](get-started-with-teams-quick-start.md)」を参照してください。

Teams を広く展開する前に、[[準備ができていることを確認してください]](get-started-with-teams-quick-start.md#make-sure-youre-ready) の項目を確認して、組織の準備ができていることを確認してください。

必要なセクションにジャンプしてください。

- [ワークロード](#workloads)
  - [チャット、チーム、チャネル](#chat-teams-and-channels)
  - [ミーティングと会議](#meetings-and-conferencing)
  - [通話プランが設定された Teams 電話](#teams-phone-with-calling-plan)
- [クライアントの展開](#deploy-clients)
- [トレーニング](#training)

## <a name="workloads"></a>ワークロード
### <a name="chat-teams-and-channels"></a>会話、チーム、チャネル

チャット、チーム、およびチャネルは、Teams の基礎部分です。 **チャット** では、1 人または複数のユーザーと会話したり、ファイルを共有したり、非公開で会話したりすることができます。 **チーム** は、組織内のすべてのユーザーに表示することも、チームのメンバーだけに表示することもできます。チームを使えば、長期プロジェクトの実施から誕生日パーティーの計画まで、あらゆるタスクやイベントに関するコラボレーションを必要なユーザーの間で実現できます。 チーム内の **チャネル** は、トピック、プロジェクト、部門、またはチームに関連するその他の事項をセグメント化できます。 チャット、チーム、およびチャネルの詳細については、「[チームとチャネルの概要](teams-channels-overview.md)」を参照してください。

> [!TIP]
> Microsoft Learn の [[Microsoft Teams の管理]](/learn/modules/m365-teams-collab-manage-teams/) モジュールを完了して、チームの役割、アクセス、およびメッセージング ポリシーを管理する方法を確認してください。

チームおよびチャネルの展開を検討するときは、チームやチャネルの作成権限を与えるユーザー、組織外のゲストがチームやチャネルにアクセスすることを許可するかどうかなどを決定する必要があります。 「[Microsoft Teams のチャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)」の記事では、チャット、チーム、およびチャネルの計画に関する多くの情報が提供されています。以下は、この記事に記載されている主な検討事項です。 それぞれの判断事項を選択すると、詳細を確認できます。

| 判断事項 | 説明 |
|--|--|
| [Teams 管理者は誰にすればよいですか?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | 管理者の役割を使用して、Teams を管理するユーザーに特定のアクセス許可を付与できます。 小規模ビジネスの場合は、1 人のユーザーが Teams のすべての側面を担当している場合があるため、これらの追加の役割を割り当てる必要がないかもしれません。 管理者は後からいつでも追加または削除できます。<br><br>[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md) |
| [Teams の所有者やメンバーの役割は、誰に割り当てればよいですか?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | Teams の所有者は、チームとそのチャネルにアクセスできるユーザーを制御します。 所有者は、チームまたはチャネルを (組織に対して) パブリックにするかプライベートにするかを決定し、チャネルをモデレートする必要があるかどうかなどのポリシーを設定できます。 メンバーは、チームとそのチャネルにアクセスでき (チャネルがプライベートに設定されていて、そのチャネルのメンバーでない場合を除きます)、また、モデレーターとして指名を受けることができます。<br><br>[Microsoft Teams でチーム所有者とメンバーを割り当てる](assign-roles-permissions.md) |
| [ゲスト アクセスは有効にする必要がありますか?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |ゲスト アクセスを使用すると、組織内の人々が組織外の人々をチームやチャネルに招待できます。 ゲスト アクセスは多くの場合、組織との間に雇用関係などの正式な関係を持たない組織外のユーザーとコラボレーションするために使用されます。 たとえば、プロジェクト プランナーを招待して、プロジェクトに一時的に参加してもらうことができます。<br>ゲスト アクセスは外部アクセスとは異なります。 ゲスト アクセスは、特定の個人のアクセスを招待して、組織内の人々と対話します。  <br>ゲスト アクセスは、既定で **オフ** になっています。 <br><br>[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)  |

上記以外に、ユーザーがチャット、チーム、およびチャネルの使用を開始できるようにするために管理者が行う必要がある操作はありません。 ただし、Teams の利用方法を管理するためのさまざまなオプションがあります。 今すぐ変更することも、Teams の実際の利用状況を確認してから変更することもできます。 詳細については、次の記事を参照してください。

- [Teams のメッセージング ポリシーを管理する](messaging-policies-in-teams.md)
- [Teams の設定](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>ミーティングと会議

ミーティングと会議により、組織内の人々は互いに、また組織外の人々とも会うことができます。 Microsoft Teams または Skype for Business のクライアントを持っているすべてのユーザーは、招待された **会議** に参加できます。 デバイスのマイク、カメラ、画面を使用することで、参加者は電話を使わなくても会話に参加できます。 参加者は、PC またはモバイル デバイスを使用して他の参加者とチャットおよび音声通話を行え、ビデオやアプリを共有することも可能です。

**電話会議** では、参加者は会議の電話番号に電話をかけ、会議 ID を入力することにより、通常の電話から会議に参加できます。 電話会議は、参加者のインターネット接続が良好でない場合、会議が音声のみである場合、またはその他の事情により Teams クライアントを使って参加できない場合に役立ちます。

> [!TIP]
> Microsoft Learn の Microsoft Teams モジュールを使用して、「[Microsoft Teams で会議とイベントを管理する](/learn/modules/m365-teams-collab-manage-meetings)」完了することにより、会議およびイベントに精通します。

Teams では既定で会議が有効になっていますが、主催者と参加者の会議エクスペリエンスを制御できます。 また、会議の前および会議中に、ユーザーが実行できることおよび実行できないことについてのポリシーを設定することもできます。 詳細については、次の記事を参照してください。

- [管理者向けクイック スタート - Microsoft Teams での会議とライブ イベント](quick-start-meetings-live-events.md)
- [中小企業向けに音声会議を設定する](audio-conferencing-smb.md)

### <a name="teams-phone-with-calling-plan"></a>通話プランが設定された Teams 電話

通話プランが設定された Microsoft 365 Teams 電話は、オフィスの電話システムのすべての機能を提供する、ユーザー数が 300 人未満の企業に適したソリューションです。 Teams 電話には、ボイスメール、発信者 ID、電話システム メニュー、フリーダイヤル番号などが含まれ、複雑でコストのかかるオンプレミスの電話システムを管理する必要はありません。

中小企業向けの通話プランが設定された Teams 電話の詳細については、「[中小企業向け Microsoft Teams 電話ガイダンス](/microsoftteams/business-voice/whats-business-voice)」を参照してください。

## <a name="deploy-clients"></a>クライアントの展開

ユーザーが Teams の使用を開始する準備ができたら、ユーザーは Teams クライアントを Windows、Mac、Linux PC、および Android または iOS デバイスにインストールできます。ユーザーは Teams クライアントを <https://teams.microsoft.com/downloads> から直接ダウンロードできます。

Teams を使用する予定のすべてのユーザーが Teams ライセンスを持っていることを確認してください。 Teams ライセンスの割り当ての詳細については、「[Teams へのユーザー アクセスを管理する](user-access.md#using-the-microsoft-365-admin-center)」を参照してください。

> [!TIP]
> Microsoft Learn の「[Microsoft Teams クライアントを展開する](/learn/modules/m365-teams-collab-deploy-clients/)」モジュールを完了して、Teams クライアントの展開を計画する方法に関する推奨事項を確認してください。

組織で Microsoft Endpoint Configuration Manager、グループ ポリシー、またはサード パーティの配布メカニズムを使用してソフトウェアをユーザーのコンピューターに展開する場合は、「[Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする](msi-deployment.md)」を参照してください。

Teams クライアントの展開に関する詳細情報については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」を参照してください。

## <a name="training"></a>トレーニング

Teams の使用に関するトレーニングをユーザーに提供する方法については、「[Microsoft Teams のトレーニング](training-microsoft-teams-landing-page.md)」を参照してください。