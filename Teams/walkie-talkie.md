---
title: Microsoft Teams のトランシーバー アプリ
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: IT 管理者の観点から、Microsoft Teams で Walkie Talkie アプリを構成する方法。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.date: 11/17/2022
ms.openlocfilehash: c4184e82e99fa4f3169fea14c62f3a892750bf8c
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845894"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams のトランシーバー アプリ

Teams の Walkie Talkie アプリは、チームにインスタント プッシュツートーク (PTT) 通信を提供し、Android と iOS で利用できます。 トランシーバーを使用すると、ユーザーは、メンバーと同じ基本チャネルを使用してチームとつながることができます。

チャネルで Walkie Talkie に接続するユーザーのみが参加者になり、PTT を使用して相互に通信できます。 [切断] をタップするまで、ユーザーは引き続き送信を受け取  **ります**。

Teams の Walkie Talkie を使用すると、ユーザーはかさばるラジオを持ち歩く必要なく、使い慣れた PTT エクスペリエンスと安全に通信でき、Walkie Talkie は WiFi または携帯ネットワーク接続でどこでも動作します。

> [!NOTE]
> トランシーバーは現在、中国では利用できません。

## <a name="license-requirements"></a>ライセンス要件

Walkie Talkie は、[Microsoft 365 および Office 365 サブスクリプション](/office365/servicedescriptions/teams-service-description)の Teams のすべての有料ライセンスに含まれています。 Teams の入手の詳細については、「[Microsoft Teams を入手操作方法」](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)を参照してください。

## <a name="deploying-walkie-talkie"></a>トランシーバーの展開

Walkie Talkie は、Google Mobile Services (GMS) と iOS デバイスを使用する Android デバイスでサポートされています。

### <a name="step-1-make-sure-walkie-talkie-is-enabled-in-your-organization"></a>手順 1: 組織で Walkie Talkie が有効になっていることを確認する

既定では、Walkie Talkie アプリは組織内のすべての Teams ユーザーに対して有効になっています。

Microsoft Teams 管理センターの [アプリの [管理](manage-apps.md) ] ページで、アプリを組織レベルで使用できるかどうかを制御します。 組織でアプリが有効になっていることを確認するには:

1. Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. アプリの一覧で、Walkie Talkie アプリを検索して選択し、[ **状態** ] トグルが **[許可**] に設定されていることを確認します。

組織内の特定のユーザーが Walkie Talkie を使用することを許可またはブロックする場合は、[ [アプリの管理](manage-apps.md) ] ページで、組織に対して Walkie Talkie が有効になっていることを確認します。 次に、アプリのアクセス許可のカスタム ポリシーを作成し、それらのユーザーに割り当てます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

### <a name="step-2-pin-walkie-talkie-to-teams"></a>手順 2: トランシーバーを Teams にピン留めする

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>調整済みの現場アプリ エクスペリエンスを使用して、Walkie Talkie やその他のアプリを Teams にピン留めする

Teams のカスタマイズされたフロントライン アプリ エクスペリエンスは、 [F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)を持つユーザーにとって Teams で最も関連性の高いアプリをピン留めします。 ピン留めされたアプリには、Walkie Talkie、Shifts、Tasks、Approvals が含まれます。 既定では、この機能はオンになっており、現場の従業員はニーズに合わせてすぐに使えるエクスペリエンスを提供します。

アプリは、ユーザーがすばやく簡単にアクセスできる Teams モバイル クライアントの下部にあるアプリ トレイにピン留めされています。

その他設定したアプリ ポリシーでのエクスペリエンスの動作など、詳細については、「[現場の従業員向けの Teams アプリの調整](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)」を参照してください。

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>アプリセットアップ ポリシーを使用して Walkie Talkie を Teams にピン留めする

アプリのセットアップ ポリシーを使用すると、チームをカスタマイズして、ユーザーにとって最も重要なアプリをユーザーに固定できます。

ユーザーの Walkie Talkie アプリをピン留めするには、グローバル (組織全体の既定) ポリシーを編集するか、アプリセットアップ ポリシーでカスタム ポリシーを作成して割り当てます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を参照してください。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="[ピン留めされたアプリの追加] ウィンドウのピン留めされたアプリの一覧に Walkie Talkie を追加するスクリーンショット。" lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>ネットワーク ドキュメント

Teams のトランシーバーにはインターネット接続が必要です。 最適なエクスペリエンスを実現するには、次のネットワーク条件が必要です。

|測定基準 | 必須 |
|---|---|
|遅延 (RTT) | < 300 ミリ秒 |
|ジッター |30 ミリ秒未満 |
|パケット損失 |< 1% |

上記のように、IP ネットワークを介したリアルタイム メディアの品質は、ネットワーク接続の品質、特に次の量によって大きく影響されます。

- **待機時間** - ネットワーク上のポイント A からポイント B までの IP パケットを取得するのにかかる時間。 このネットワーク伝達遅延は、基本的に、2 つのポイント間の物理的な距離と光の速度に関連付けられています。これには、その間のさまざまなルーターによって発生するオーバーヘッドが増えます。 遅延は往復時間 (RTT) として測定されます。
- **到着間ジッター** - 連続するパケット間の遅延の平均変化。
- **パケット損失** - パケット損失は、多くの場合、特定の期間内に失われるパケットの割合として定義されます。 パケット損失は、影響がほとんどない小さな個々の失われたパケットから、完全なオーディオカットアウトを引き起こすバックツーバックバースト損失まで、オーディオ品質に直接影響します。

Walkie Talkie からの予想されるデータ使用量は、オーディオの送受信時に約 20 Kb/秒です。 アイドル状態の場合、トランシーバーからの予想されるデータ使用量はごくわずかです。

## <a name="walkie-talkie-devices"></a>トランシーバー デバイス

現場担当者は、電話がロックされている場合でも、多くの場合、トランシーバーの通話を話したり受け取ったりする必要があります。 この体験は、専用の PTT ボタンを備えた専用デバイスを介して可能です。

#### <a name="headsets"></a>ヘッドセット

- ワイヤレス ヘッドセット (iOS と Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- 有線ヘッドセット (Android のみ)
  - [クライン エレクトロニクス](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>堅牢な Android スマートフォン

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-x4-1001010801327.html)、 [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html)、 [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html)、 [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html)、 [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - 手動セットアップ: Teams がインストールされたら、[ **設定** > **] ボタン** に移動します。 [専用] ボタン (1 または 2) で、[ **長押** し] を選択し、[ **PTT アプリ**] を選択します。 [ **カスタム**] の横にある青いホイールを選択し、[Teams] を選択 **します**。
- 京セラ [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) と [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - 手動セットアップ: Teams がインストールされたら、[**設定] [プログラミング可能なキー****]** >  に移動します。 **[PTT キー**] または [**長押し** ] (デバイスに応じて) を選択し、[Teams] を選択 **します**。
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer), [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer), [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp), [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer), [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer), [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer), 
  - 手動セットアップ: Teams がインストールされている場合、専用 PTT ボタンは既定で Walkie Talkie で動作します。
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - 手動セットアップ: Teams がインストールされたら、[**設定]****[詳細設定** > ]**[XCover/Active キー**]  >  の順に移動します。 アプリで **[コントロール XCover キー] を** オンにし、[Teams] を選択 **します**。
  - [MDM のセットアップ](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - 手動セットアップ: Teams がインストールされたら、[**設定] [プログラマブル キー****]** >  の順に移動します。 [ **PTT キー アプリの選択]** を選択し、[Teams] を選択 **します**。
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html)、 [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html)、 [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html)、 [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html)、 [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html)、 [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html)、 [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - 手動セットアップ: Teams がインストールされている場合、専用 PTT ボタン (LEFT_TRIGGER_2) は既定で Walkie Talkie と連携します。

> [!NOTE]
> これらのデバイスは Teams 認定を受けていません。 Teams トランシーバーで動作することが検証されています。

## <a name="bluetooth-devices"></a>Bluetooth デバイス

> [!NOTE]
> ユーザーが Bluetooth アクセサリを使用している場合は、モバイル デバイス管理 (MDM) ソリューションで Bluetooth デバイスがブロックされていないことを確認します。

Android OS バージョン 12 以降を実行しているデバイスでは、Bluetooth アクセス許可が必要であり、BLE スタックを使用して接続するための場所のアクセス許可は不要になりました。 Teams レベルで "近くのアクセス許可" が付与されていない場合、ユーザーは Bluetooth アクセス許可のプロンプトを受け取ります。 ヘッドセットなどの Bluetooth アクセサリがデバイスに接続されているかどうかに関わらず、このプロンプトが表示されます。 Bluetooth アクセサリが接続されている場合は、[ **許可]** をタップすると、Walkie Talkie が Bluetooth アクセサリに接続されます。

## <a name="get-insight-into-walkie-talkie-usage-and-performance"></a>Walkie Talkie の使用状況とパフォーマンスに関する分析情報を取得する

Teams 管理センターの [Walkie Talkie の使用状況とパフォーマンス レポート](teams-analytics-and-reports/walkie-talkie-usage-report.md) には、組織内の Walkie Talkie アクティビティとパフォーマンスの概要が表示されます。 レポートには、行われた PTT 転送の数、受信した PTT 転送の数、チャネル アクティビティ、転送期間、デバイスと参加者の詳細などの情報が表示されます。

## <a name="more-information"></a>詳細情報

- ユーザーがモバイル データを使用して Teams 経由で通信している場合、Walkie Talkie は同じ方法を使用します。
- トランシーバーは、低帯域幅の状況、またはスマートフォンが接続されて機能している状況でうまく機能するはずです。 トランシーバーは、接続がまったくない場合は機能しません。

エンド ユーザー エクスペリエンスの詳細については、次を参照してください。

- [Teams トランシーバーの使用を開始する](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [トランシーバーを使用してチームと通信する](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
