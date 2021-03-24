---
title: Microsoft Teams のトランシーバー アプリケーション
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin の観点から、Microsoft Teams でトランシーバー アプリを構成する方法です。
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
ms.openlocfilehash: 90d5135196de9ecf62085e88053d80299b6e5a58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097463"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams のトランシーバー アプリ

Teams のトランシーバー アプリは、Teams にインスタント プッシュツートーク (PTT) 通信を提供し、Android で利用できるようになりました。 トランシーバーを使用すると、ユーザーは、メンバーと同じ基本チャネルを使用してチームとつながることができます。 チャネルでトランシーバーに接続するユーザーのみが参加者になり、プッシュツートークを使用して一度に 1 つずつ相互に通信できます。

Teams の Walkie Talkie を使用すると、Frontline の作業者は、バルク ラジオを運ぶ必要なく、使い慣れた PTT エクスペリエンスで安全に通信できます。また、Walkie Talkie は WiFi または携帯電話のインターネット接続を使用してどこからでも作業できます。

## <a name="getting-started"></a>はじめに

### <a name="deploying-walkie-talkie"></a>トランシーバーの展開

現在、トランシーバーはプリインストールされていません。 組織内のユーザーに対してこの機能を有効にするには、[[Teams 管理センター]](https://admin.teams.microsoft.com/) からユーザーに割り当てられた [アプリ セットアップ ポリシー](teams-app-setup-policies.md) にトランシーバーを追加する必要があります。

有効にすると、トランシーバーは 48 時間以内に Android アプリで利用できるようになります。

### <a name="adding-walkie-talkie-to-your-app-list"></a>トランシーバーをアプリ リストに追加する

Microsoft Teams 管理センターの **[Teams アプリ]** > **[セットアップ ポリシー]** で、**[ユーザーのピン留めを許可]** を **[オン]** に設定する必要があります。 次に、「ピン留めされたアプリ」セクションで、**[アプリの追加]** をクリックします。

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="「ピン留めされたアプリ」セクションと選択する [アプリの追加] ボタンが表示されます。":::

右側に表示される **[ピン留めされたアプリを追加]** パネルで、**[検索]** テキストボックスを使用してトランシーバーを探します。 検索結果として保存されている場合は、名前の右側にある[追加] ボタンを選択してリストに追加します。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="検索ウィンドウにトランシーバーが入力された [ピン留めされたアプリを追加] サイドバーと、検索結果にトランシーバー アプリが表示され、その横に [追加] ボタンが表示されます。":::

トランシーバー アプリが [ピン留めされたアプリ] リストに表示され、**[保存]** ボタンをクリックすると使用できるようになります。

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="トランシーバー アプリが追加されたピン留めされたアプリのリストと、リストの下にある [保存] ボタンが表示されます。":::

### <a name="network-documentation"></a>ネットワーク ドキュメント

Teams のトランシーバーにはインターネット接続が必要であり、最適なエクスペリエンスを得るには以下のネットワーク条件が必要です。

|測定基準 | 必須 |
|---|---|
|遅延 (RTT) | < 300 ミリ秒 |
|ジッター |< 30 ミリ秒 |
|パケット損失 |< 1% |

上記のように、IP ネットワークを介したリアルタイム メディアの品質は、ネットワーク接続の品質、特に次の量によって大きく影響されます。

- **遅延** - これは、IP パケットがネットワーク上のポイント A からポイント B に到達するまでにかかる時間です。 このネットワーク伝達遅延は、基本的に、2 つのポイントと光の速度の間の物理的な距離に結び付き、その間にあるさまざまなルーターによって発生するオーバーヘッドが多く含まれています。 遅延は往復時間 (RTT) として測定されます。
- **パケット損失** - これは、指定した時間帯に失ったパケットの割合として定義されることがよくあります。 パケット損失は、オーディオの品質に直接影響を与えます。ほとんど影響を及ぼすことのない小規模のパケット損失から、音声が完全に途切れる原因となる連続したバースト損失まで存在します。
- **ジッタ** - これは、連続するパケット間の遅延の平均変動です。

トランシーバーからの予想データ使用量は、オーディオの送受信時に約 20KB/秒です。 アイドル状態の場合、トランシーバーからの予想されるデータ使用量はごくわずかです。

### <a name="walkie-talkie-devices"></a>トランシーバー デバイス

最前線の従業員は、多くの場合、自分の電話がロックされている場合でも、Walkie Talkie の通話を話して受ける必要があります。 この体験は、専用の PTT ボタンを備えた専用デバイスを介して可能です。

- ヘッドセット
  - 有線ヘッドセット ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))
  - ワイヤレス ヘッドセット ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))
- 頑丈な電話
  - Samsung Galaxy XCover Pro
    - [詳細情報](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)。
    - [セットアップ ガイド](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。

> [!NOTE]
> これらのデバイスは Teams 認定を受けていません。 Teams トランシーバーで動作することが検証されています。

### <a name="license-requirements"></a>ライセンス要件

トランシーバー アプリは、[Office 365 サブスクリプション](/office365/servicedescriptions/teams-service-description)の Teams のすべての有料ライセンスに含まれています。 Teams の入手方法の詳細については、「 [Microsoft Teams へのアクセス方法](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)」を参照してください。

> [!NOTE]
> 特定の高度な機能には、追加のライセンスが必要な場合があります。 たとえば、Samsung Galaxy XCover Pro との統合には Knox ライセンスが必要です。

## <a name="further-information"></a>詳細情報

- ITAdmins は、アプリ ポリシーを通じてトランシーバーを使用しているユーザーの制御を維持できます。
- フロントライン ワーカーがモバイル データを使用して Teams 経由で通信している場合、Walkie Talkie も同じ方法を使用します。
- トランシーバーは、低帯域幅の状況、またはスマートフォンが接続されて機能している状況でうまく機能するはずです。 接続がまったくない場合、トランシーバーは機能しません。

エンドユーザー エクスペリエンスの詳細については、以下を参照してください。

- [Teams トランシーバーの使用を開始する](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [トランシーバーを使用してチームと通信する](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)