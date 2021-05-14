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
ms.openlocfilehash: 9f86d40772eb067a561708c6170ef2354bae521b
ms.sourcegitcommit: 05411575d07d3eadc79d872d1cf81b36aae25621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "52479074"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams のトランシーバー アプリ

Teams のトランシーバー アプリは、Teams にインスタント プッシュツートーク (PTT) 通信を提供し、Android で利用できるようになりました。 トランシーバーを使用すると、ユーザーは、メンバーと同じ基本チャネルを使用してチームとつながることができます。 チャネルでトランシーバーに接続するユーザーのみが参加者になり、プッシュツートークを使用して一度に 1 つずつ相互に通信できます。

Teams の Walkie Talkie を使用すると、フロントライン の作業員は、バルクラジオを持ち歩く必要なく、使い慣れた PTT エクスペリエンスと安全に通信できます。また、Walkie Talkie は WiFi や携帯電話のインターネット接続でどこからでも動作します。

## <a name="getting-started"></a>はじめに

### <a name="deploying-walkie-talkie"></a>トランシーバーの展開

現在、Walkie Talkie は Google Mobile Services (GMS) を搭載した Android デバイスで使用できます。また、事前にインストールされていません。 組織内のユーザーに対してこの機能を有効にするには、[[Teams 管理センター]](https://admin.teams.microsoft.com/) からユーザーに割り当てられた [アプリ セットアップ ポリシー](teams-app-setup-policies.md) にトランシーバーを追加する必要があります。 有効にすると、トランシーバーは 48 時間以内に Android アプリで利用できるようになります。

### <a name="adding-walkie-talkie-to-your-app-list"></a>トランシーバーをアプリ リストに追加する

Microsoft Teams 管理センターの **[Teams アプリ]** > **[セットアップ ポリシー]** で、**[ユーザーのピン留めを許可]** を **[オン]** に設定する必要があります。 次に、「ピン留めされたアプリ」セクションで、**[アプリの追加]** をクリックします。

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="「ピン留めされたアプリ」セクションと選択する [アプリの追加] ボタンが表示されます。":::

右側に表示される **[ピン留めされたアプリを追加]** パネルで、**[検索]** テキストボックスを使用してトランシーバーを探します。 検索結果として使用する場合は、名前の右側にある[追加] ボタンを選択してリストに追加します。

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

- **遅延** - これは、IP パケットがネットワーク上のポイント A からポイント B に到達するまでにかかる時間です。 このネットワーク伝達遅延は、基本的に、2 つのポイント間の物理的な距離と光の速度に関連付けられます。これには、その間のさまざまなルーターによって発生するオーバーヘッドが多く含まれています。 遅延は往復時間 (RTT) として測定されます。
- **到着間ジッター** - 連続するパケット間の遅延の平均変化です。
- **パケット損失** - これは、指定した時間帯に失ったパケットの割合として定義されることがよくあります。 パケット損失は、オーディオの品質に直接影響を与えます。ほとんど影響を及ぼすことのない小規模のパケット損失から、音声が完全に途切れる原因となる連続したバースト損失まで存在します。

Walkie Talkie からの予想されるデータ使用量は、音声の送受信時に約 20 Kb/s です。 アイドル状態の場合、トランシーバーからの予想されるデータ使用量はごくわずかです。

### <a name="walkie-talkie-devices"></a>トランシーバー デバイス

多くの場合、フロントラインワーカーは、携帯電話がロックされている場合でも、Walkie Talkie の通話を話して受信する必要があります。 この体験は、専用の PTT ボタンを備えた専用デバイスを介して可能です。

- **ヘッドセット**
  - ワイヤレス ヘッドセット 
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - 有線ヘッドセット 
    - [クライン電子](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **頑丈な電話**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/) [、Galaxy XCover 5、Galaxy](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy)Tab Active [3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    -  手動セットアップ - インストールTeams、XCover/Active キー設定 >高度>に移動します。 [アプリで XCover キーを制御する] をオンにし、[Teams] を選択します。
    -  [MDM のセットアップ](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> これらのデバイスは Teams 認定を受けていません。 Teams トランシーバーで動作することが検証されています。

### <a name="license-requirements"></a>ライセンス要件

トランシーバー アプリは、[Office 365 サブスクリプション](/office365/servicedescriptions/teams-service-description)の Teams のすべての有料ライセンスに含まれています。 Teams の入手方法の詳細については、「 [Microsoft Teams へのアクセス方法](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)」を参照してください。

> [!NOTE]
> 特定の高度な機能には、追加のライセンスが必要な場合があります。 たとえば、Samsung Galaxy XCover Pro との統合には Knox ライセンスが必要です。

## <a name="further-information"></a>詳細情報

- ITAdmins は、アプリ ポリシーを通じてトランシーバーを使用しているユーザーの制御を維持できます。
- Frontline worker がモバイル データを使用して Teams 経由で通信している場合、Walkie Talkie は同じ方法を使用します。
- トランシーバーは、低帯域幅の状況、またはスマートフォンが接続されて機能している状況でうまく機能するはずです。 接続がまったくない場合、トランシーバーは機能しません。

エンドユーザー エクスペリエンスの詳細については、以下を参照してください。

- [Teams トランシーバーの使用を開始する](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [トランシーバーを使用してチームと通信する](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
