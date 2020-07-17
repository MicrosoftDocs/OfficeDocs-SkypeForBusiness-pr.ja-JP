---
title: Microsoft Teams での internet explorer のトランシーバーアプリケーション
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin の観点から、Microsoft Teams でトランシーバー Ie のアプリを構成する方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043012"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams での ie トランシーバーアプリの解説

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Teams のトランシーバー Ie のアプリでは、チームのインスタントプッシュツートーク (PTT) コミュニケーションが提供されます。これは、Android のパブリックプレビューで間もなく利用可能になります。 トランシーバー ie では、ユーザーは、メンバーである基になるチャネルを使ってチームと接続できます。 チャネルで、トランシーバーに接続しているユーザーのみが、チャネルで参加者になり、プッシュツートークを使って互いに通信できます。

Teams でトランシーバー Ie の機能を使用することで、firstline worker は、非常に強い無線を伝送することなく、使い慣れた PTT エクスペリエンスと安全に通信できるようになりました。また、WiFi または携帯電話のインターネット接続があればどこでも Ie トランシーバーが動作します。

## <a name="getting-started"></a>はじめに

### <a name="deploying-walkie-talkie"></a>解説した Ie トランシーバーの展開

パブリックプレビュー中に、再生済み Ie トランシーバーがプリインストールされていない。 組織内のユーザーに対してこの機能を有効にするには、 [App Setup Policy](teams-app-setup-policies.md)   [Teams 管理センター](https://admin.teams.microsoft.com/)のユーザーに割り当てられているアプリセットアップポリシーに、トランシーバーした ie のを追加する必要があります。

有効にすると、48時間以内に Android アプリで利用できるようになります。

### <a name="adding-walkie-talkie-to-your-app-list"></a>登録した Ie トランシーバーをアプリの一覧に追加する

Microsoft teams 管理センターの [ **Teams アプリ**  >  **セットアップポリシー**] で、**ユーザーの固定**を **[オン**] に設定しておく必要があります。 次に、[固定されたアプリ] セクションで、[ **+ アプリの追加**] をクリックします。

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="[固定されたアプリ] セクションと [アプリの追加] ボタンを選んで表示します。":::

右側に表示される [固定された**アプリの追加**] パネルで、[**検索**] ボックスを使用して、「トランシーバー」という ie の説明を探します。 検索結果として表示されたら、名前の右側にある [**追加**] ボタンをクリックして、リストに追加します。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="検索ウィンドウと検索した Ie トランシーバーアプリの横にある [追加] ボタンをクリックして、[ピン留めされたアプリの追加] サイドバーを表示します。":::

これで、このアプリを [ピン留めされたアプリ] の一覧に表示されるようになり、[**保存**] ボタンをクリックすると使用できるようになります。

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="[挿入済みの Ie トランシーバーアプリが追加され、リストの下に [保存] ボタンが追加された、ピンされたアプリの一覧を示します。":::

### <a name="network-documentation"></a>ネットワークドキュメント

トランシーバー Teams での ie の紹介は、インターネット接続が必要です。また、最適なエクスペリエンスを実現するには、ネットワークの条件が必要です。

Latency (RTT) < 300ms |ジッター < 30ms |パケット損失 < 1%

上で説明したように、IP ネットワーク上のリアルタイムメディアの品質は、ネットワーク接続の品質に大きな影響を与えますが、特に次の量によって影響を受けます。

- **待機**時間-この時刻は、IP パケットがネットワーク上のポイント B からポイント B に到達するまでの時間です。 このネットワーク伝達遅延は、さまざまなルーターの間の追加のオーバーヘッドを含めて、2 つのポイントの間の物理的な距離と光速度に関連しています。 待ち時間はラウンドトリップ時間 (RTT) として測定されます。
- [**パケット損失**]: 特定の時間帯に失われるパケットのパーセンテージとして定義されることがよくあります。 パケット損失は、オーディオの品質に直接影響を与えます。これは、完全に失われた小さいパケットによって、完全なオーディオのカットアウトを引き起こすバックツーバックのバースト損失になります。
- **ジッタ**-連続したパケット間の遅延の平均変化を示します。

データ使用量は、「音楽を送信または受信するときに 20KB/s」からトランシーバーます。 アイドル状態の場合、トランシーバー Ie のデータ使用量はごくわずかです。

### <a name="walkie-talkie-devices"></a>お互いの ie トランシーバーデバイス

FirstLine worker は、多くの場合、電話がロックされているときでも、聞く Ie トランシーバーの通話を発信したり、受信したりする必要があります。 この操作は、専用の PTT ボタンを持つ専用デバイスから実行できます。

- 既存の電話
  - 有線ヘッドセット ([Klein エレクトロニクス](https://www.kleinelectronics.com/))
  - ワイヤレスヘッドセット ([Jabra BlueParrott](https://www.blueparrott.com/))
- 丈夫の携帯電話
  - Samsung Galaxy XCover Pro
    - [さらに詳しい情報](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)があります。
    - [セットアップガイド](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。

> [!NOTE]
> これらのデバイスは Teams で認定されているわけではありません。 チームの内容を確認した Ie トランシーバーで動作することが検証されました。

### <a name="license-requirements"></a>ライセンス要件

このアプリは、 [Office 365 サブスクリプション](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)のすべての有料ライセンスに含まれています。 Teams の入手方法について詳しくは、「 [Microsoft teams にアクセスする方法](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)」をご覧ください。

> [!NOTE]
> 一部の高度な機能には追加のライセンスが必要です。 たとえば、Samsung Galaxy XCover Pro との統合には、Knox ライセンスが必要です。

## <a name="further-information"></a>さらに詳しい情報

- ITAdmins は、アプリのポリシーを通じて、トランシーバーの Ie を使用しているユーザーを管理することができます。
- 最初のラインワーカーがモバイルデータを使って Teams で通信している場合、トランシーバーは同じメソッドを使います。
- トランシーバー ie は、低帯域幅の状況でも適切に動作する必要があります。または、スマートフォンが接続され、動作している場合に適しています。 トランシーバーは、接続されていない場合は機能しません。

エンドユーザーエクスペリエンスの詳細については、以下を参照してください。

- [チームを活用する Ie トランシーバーの使用を開始する](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [トランシーバー Ie のお客様のチームとコミュニケーションする](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
