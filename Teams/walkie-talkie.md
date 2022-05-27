---
title: Microsoft Teams のトランシーバー アプリ
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin の観点から、Microsoft Teams でトランシーバー アプリを構成する方法です。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e311fb94996e1c51bb5f73190539cd0e1f9f127
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681898"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams のトランシーバー アプリ

Teamsの Walkie Talkie アプリは、チームに即座にプッシュツートーク (PTT) 通信を提供し、Android & iOSで利用できるようになりました。 トランシーバーを使用すると、ユーザーは、メンバーと同じ基本チャネルを使用してチームとつながることができます。 チャネルでトランシーバーに接続するユーザーのみが参加者になり、プッシュツートークを使用して一度に 1 つずつ相互に通信できます。

Teamsの Walkie Talkie を使用すると、現場のワーカーは、かさばるラジオを持ち運ぶ必要なく、使い慣れた PTT エクスペリエンスと安全に通信できるようになり、Walkie Talkie は WiFi または携帯インターネット接続を使用してどこでも動作します。

> [!NOTE]
> Walkie Talkie は現在、中国では利用できません。

## <a name="getting-started"></a>はじめに

### <a name="deploying-walkie-talkie"></a>トランシーバーの展開

Walkie Talkie は、Google Mobile Services (GMS) および iOS デバイスを使用するAndroid デバイスでサポートされています。

### <a name="pin-walkie-talkie-to-teams"></a>Walkie Talkie をTeamsにピン留めする

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>カスタマイズされたフロントライン アプリ エクスペリエンスを使用して、Walkie Talkie やその他のアプリをTeamsにピン留めする

Teamsのカスタマイズされたフロントライン アプリ エクスペリエンスは、[F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)を持つユーザーにとってTeamsで最も関連性の高いアプリをピン留めします。 ピン留めされたアプリには、Walkie Talkie、Shifts、Tasks、承認が含まれます。 既定では、この機能はオンになっており、現場のワーカーはニーズに合わせてすぐに使えるエクスペリエンスを提供します。

アプリは、アプリ バー (Teams デスクトップ クライアントの側とTeamsモバイル クライアントの下部にあるバー) にピン留めされ、ユーザーはすばやく簡単にアクセスできます。

設定したアプリ ポリシーでのエクスペリエンスの動作など、詳細については、「[現場のワーカー向けにアプリTeamsを調整する](pin-teams-apps-based-on-license.md)」を参照してください。

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>アプリセットアップ ポリシーを使用して Walkie Talkie をTeamsにピン留めする

アプリのセットアップ ポリシーを使用すると、Teamsをカスタマイズして、ユーザーのユーザーにとって最も重要なアプリをピン留めできます。

ユーザーの Walkie Talkie アプリをピン留めするには、グローバル (組織全体の既定) ポリシーを編集するか、カスタム アプリ設定ポリシーを作成して割り当てることができます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を参照してください。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="[ピン留めされたアプリの追加] ウィンドウのピン留めされたアプリの一覧に Walkie Talkie を追加する方法を示すスクリーンショット。" lightbox="media/deploy-walkie-talkie-2.png":::

### <a name="network-documentation"></a>ネットワーク ドキュメント

Teams のトランシーバーにはインターネット接続が必要であり、最適なエクスペリエンスを得るには以下のネットワーク条件が必要です。

|測定基準 | 必須 |
|---|---|
|遅延 (RTT) | < 300 ミリ秒 |
|ジッター |30 ミリ秒未満 |
|パケット損失 |< 1% |

上記のように、IP ネットワークを介したリアルタイム メディアの品質は、ネットワーク接続の品質、特に次の量によって大きく影響されます。

- **遅延** - これは、IP パケットがネットワーク上のポイント A からポイント B に到達するまでにかかる時間です。 このネットワーク伝達遅延は、基本的に、2 つのポイント間の物理的な距離と光の速度に関連しています。これには、その間のさまざまなルーターによって発生するオーバーヘッドが増えます。 遅延は往復時間 (RTT) として測定されます。
- **到着間ジッター** - これは、連続するパケット間の遅延の平均変化です。
- **パケット損失** - これは、指定した時間帯に失ったパケットの割合として定義されることがよくあります。 パケット損失は、オーディオの品質に直接影響を与えます。ほとんど影響を及ぼすことのない小規模のパケット損失から、音声が完全に途切れる原因となる連続したバースト損失まで存在します。

Walkie Talkie からの予想されるデータ使用量は、オーディオの送受信時に約 20 Kb/秒です。 アイドル状態の場合、トランシーバーからの予想されるデータ使用量はごくわずかです。

### <a name="walkie-talkie-devices"></a>トランシーバー デバイス

フロントライン ワーカーは、電話がロックされている場合でも、多くの場合、Walkie Talkie の通話を話して受信する必要があります。 この体験は、専用の PTT ボタンを備えた専用デバイスを介して可能です。

- **ヘッドセット**
  - ワイヤレス ヘッドセット (iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - ワイヤード ヘッドセット (Androidのみ)
    - [クライン エレクトロニクス](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **堅牢なAndroid電話**
  - [Samsung Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)、[Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy)、[Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - 手動セットアップ - Teamsがインストールされている場合は、XCover/Active キー>設定 >高度な機能に移動します。 [アプリで XCover キーを制御する] をオンにし、[Teams] を選択します。
    - [MDM のセットアップ](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html)、 [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html)、 [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html)、 [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html)、 [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html)、 [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html)、 [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - 手動セットアップ - Teamsがインストールされている場合、専用 PTT ボタン (LEFT_TRIGGER_2) は既定で Walkie Talkie で動作します
    
> [!NOTE]
> これらのデバイスは Teams 認定を受けていません。 Teams トランシーバーで動作することが検証されています。

### <a name="license-requirements"></a>ライセンス要件

トランシーバー アプリは、[Office 365 サブスクリプション](/office365/servicedescriptions/teams-service-description)の Teams のすべての有料ライセンスに含まれています。 Teamsの取得の詳細については、[Microsoft Teamsへのアクセス操作方法確認](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)してください。

## <a name="further-information"></a>詳細情報

- IT 管理者は、アプリ ポリシーを通じて Walkie Talkie を使用しているユーザーを制御できます。
- フロントライン ワーカーがモバイル データを使用してTeams経由で通信している場合、Walkie Talkie は同じ方法を使用します。
- トランシーバーは、低帯域幅の状況、またはスマートフォンが接続されて機能している状況でうまく機能するはずです。 接続がまったくない場合、Walkie Talkie は機能しません。

エンドユーザー エクスペリエンスの詳細については、以下を参照してください。

- [Teams トランシーバーの使用を開始する](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [トランシーバーを使用してチームと通信する](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
