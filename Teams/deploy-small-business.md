---
title: 小規模ビジネスで Microsoft Teams を設定する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 小規模ビジネスで Teams を設定して、ユーザーがチャットやファイル共有を使用して共同作業したり、大小の会議を設定して参加したり、ビデオや音声で話したりできるようにします。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bbadcd18050d098d9c602f7ba56da40ecafd89b4
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395437"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>小規模ビジネスで Microsoft Teams を設定する

Teams をカスタマイズする方法はたくさんあります。 次のセクションでは、以下にあげる Teams の各ワークロードを設定する方法を説明します。**チャット、チーム、およびチャネル**。**ミーティングと会議**。および、**クラウド ボイス**。 各ワークロードを設定する順序に決まりはありません。 最初にチャット、チーム、チャネルのワークロードを設定することをお勧めしますが、ミーティングと会議、さらにはクラウド ボイスから始めることもできます。 選択は自由です。

> [!NOTE]
> まだ行っていない場合は、パイロットから Teams の展開を開始することを強くお勧めします。 パイロットにより、計画と最終的な展開の前に、あなたや早期採用者が Teams とその機能に精通することができます。 パイロットを開始する方法の詳細については、「[Microsoft Teams を開始する](get-started-with-teams-quick-start.md)」を参照してください。

Teams を広く展開する前に、[[準備ができていることを確認してください]](get-started-with-teams-quick-start.md#make-sure-youre-ready) の項目を確認して、組織の準備ができていることを確認してください。

以下のうち、興味のあるセクションにジャンプしてください。

- [ワークロード](#workloads)
  - [チャット、チーム、チャネル](#chat-teams-and-channels)
  - [ミーティングと会議](#meetings-and-conferencing)
  - [Business Voice](#business-voice)
- [クライアントの展開](#deploy-clients)
- [トレーニング](#training)

## <a name="workloads"></a>ワークロード
### <a name="chat-teams-and-channels"></a>会話、チーム、チャネル

チャット、チーム、およびチャネルは、Teams の基礎部分です。 **チャット** では、1 人以上のユーザーが互いに話したり、ファイルを共有したり、非公開で会ったりすることができます。 **チーム** は、組織内のすべての人に表示されることも、チーム内の人だけに表示されることもあります。これにより、長期にわたるプロジェクトであれ、誕生日パーティーの計画であれ、適切な人がタスクや機会に関係なくコラボレーションできます。 チーム内の **チャネル** は、トピック、プロジェクト、部門、またはチームにとって意味のあるその他のものをセグメント化できます。 チャット、チーム、およびチャネルの詳細については、[[チームとチャネルの概要](teams-channels-overview.md)] を確認してください。

> [!TIP]
> Microsoft Learn の [[Microsoft Teams の管理]](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-teams/) モジュールを完了して、チームの役割、アクセス、およびメッセージング ポリシーを管理する方法を確認してください。

チームとチャネルの展開を検討するときは、誰がそれらを作成できるか、組織外のゲストがそれらにアクセスできるかどうかなどを決定する必要があります。 「[Microsoft Teams のチャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)」の記事には、チャット、チーム、およびチャネルの計画に関する多くの情報がありますが、その記事から考慮すべき重要な点がいくつかあります。 詳細については、決定事項をクリックしてください。

| Decision | 説明 |
|--|--|
| [Teams 管理者は誰にすればよいですか?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | 管理者の役割を使用して、Teams を管理するユーザーに特定のアクセス許可を付与できます。 同じ人が Teams のすべての側面に責任を持つ可能性があるため、小規模ビジネスではこれらの追加の役割を必要としない場合があります。 管理者は後でいつでも追加または削除できます。<br><br>[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md) |
| [Teams の所有者やメンバーの役割は、誰に割り当てればよいですか?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | Teams の所有者は、チームとそのチャネルにアクセスできるユーザーを制御します。 チームまたはチャネルを (組織に対して) パブリックにするかプライベートにするかを決定し、チャネルをモデレートする必要があるかどうかなどのポリシーを設定できます。 メンバーはチームとそのチャネルにアクセスでき (チャネルがプライベートに設定されていて、そのチャネルのメンバーでない場合を除きます)、モデレーターとして指定できます。<br><br>[Microsoft Teams でチーム所有者とメンバーを割り当てる](assign-roles-permissions.md) |
| [ゲスト アクセスは有効にする必要がありますか?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |ゲスト アクセスを使用すると、組織内の人々が組織外の人々をチームやチャネルに招待できます。 ゲスト アクセスは、組織外の、正式な関係にない人々とコラボレーションするためによく使用されます。 たとえば、プロジェクト プランナーを招待して、プロジェクトに一時的に参加してもらうことができます。<br>ゲスト アクセスは外部アクセスとは異なります。 ゲスト アクセスは、特定の個人のアクセスを招待して、組織内の人々と対話できるようにします。  <br>ゲスト アクセスは、既定で **オフ** になっています。 <br><br>[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)  |

ユーザーがチャット、チーム、およびチャネルの使用を開始するためにhs、他に何もする必要はありません。 ただし、Teams の使用方法を制御するためのオプションはたくさんあります。 今すぐ変更するか、ユーザーが Teams をどのように使用しているかがわかるまで待つことができます。 詳細については、次の記事を参照してください。

- [Teams のメッセージング ポリシーを管理する](messaging-policies-in-teams.md)
- [Teams の設定](enable-features-office-365#teams-settings)

### <a name="meetings-and-conferencing"></a>ミーティングと会議

ミーティングと会議により、組織内の人々は互いに、また組織外の人々とも会うことができます。 Teams または Skypefor Business クライアントを持っている人は誰でも、招待された **ミーティング** に参加できます。 デバイスのマイク、カメラ、画面を使用すると、参加者は電話を使わなくても会話に参加できます。 参加者は、PC またはモバイル デバイスを使用して、チャット、音声通話、およびビデオやアプリを他の参加者と共有できます。

**電話会議** では、参加者は会議の電話番号に電話をかけ、会議 ID を入力することにより、通常の電話から会議に参加できます。 電話会議は、参加者のインターネット接続が良好でない場合、会議が音声のみである場合、またはその他の状況で Teams クライアントを介して参加できない場合に役立ちます。

> [!TIP]
> Microsoft Learn の Microsoft Teams モジュールを使用して、「[Microsoft Teams で会議とイベントを管理する](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-meetings)」完了することにより、会議およびイベントに精通します。

Teams では既定で会議が有効になっていますが、主催者と参加者の会議エクスペリエンスを制御できます。 また、会議の前および会議中に、ユーザーが実行できることと許可されていないことについてのポリシーを設定することもできます。 詳細については、次の記事を参照してください。

- [管理クイック スタート - Microsoft Teams での会議とライブ イベント](quick-start-meetings-live-events.md)
- [中小企業向けの音声会議を設定する](audio-conferencing-smb.md)

### <a name="business-voice"></a>Business Voice

[Microsoft 365 Business Voice](business-voice/whats-business-voice.md) は、ユーザー数が 300 人未満の企業に最適なソリューションであり、オフィスの電話システムのすべての機能を提供します。 Business Voice には、ボイスメール、発信者 ID、電話システム メニュー、フリーダイヤル番号などが含まれ、複雑でコストのかかるオンプレミスの電話システムを管理する必要はありません。

Microsoft 365 Phone System に基づく Business Voice は、Phone System の機能とアドオンをバンドルし、電話システムの設定に役立つわかりやすいウィザードを提供することで、組織への音声の追加を簡素化します。 組織が [Business Voice をサポートする国または地域](business-voice/country-region-availability.md)にある場合は、電話番号を Microsoft 365 に転送して、電話システムを管理させることができます。

電話システムとして Microsoft 365 を使用すると、Teams クライアントをインストールすることで、任意のデバイスを電話に変えることができます。 または、従来のデスクフォンや会議用電話を使用したい場合は、多くの Teams 認定のデバイスを選択できます。 どちらの場合も、通話は常に現在地にルーティングされ、発信する通話には常にオフィスの電話番号が割り当てられます。

Business Voice の試用に興味がある場合は、「[Microsoft 365 Business Voice を使用するために購入する必要があるもの](business-voice/what-to-buy.md)」確認してください。

## <a name="deploy-clients"></a>クライアントの展開

ユーザーが Teams の使用を開始する準備ができたら、ユーザーは Teams クライアントを Windows、Mac、Linux PC、および Android または iOS デバイスにインストールできます。 ユーザーは<https://teams.microsoft.com/downloads>から直接 Teams クライアントをダウンロードできます。

Teams を使用するすべての人が Teams ライセンスを持っていることを確認してください。 Teams ライセンスの割り当ての詳細については、「[Teams へのユーザー アクセスを管理する](user-access.md#using-the-microsoft-365-admin-center)」を参照してください。

> [!TIP]
> Microsoft Learn の「[Microsoft Teams クライアントを展開する](https://docs.microsoft.com/learn/modules/m365-teams-collab-deploy-clients/)」モジュールを完了して、Teams クライアントの展開を計画する方法に関する推奨事項を入手してください。

組織で Microsoft Endpoint Configuration Manager、グループ ポリシー、またはサード パーティの配布メカニズムを使用してソフトウェアをユーザーのコンピューターに展開する場合は、「[Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする](msi-deployment.md)」を参照してください。

Teams クライアントの展開に関する詳細情報が必要な場合は、「[Microsoft Teams のクライアントを取得する](get-clients.md)」を参照してください。

## <a name="training"></a>トレーニング

Teams を使用するようにユーザーをトレーニングする方法については、「[Microsoft Teams のトレーニング](training-microsoft-teams-landing-page.md)」を参照してください。