---
title: Teams 電話システムのインターネット接続を確認する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: インターネットの準備が整っていることを確認Teams 電話システム
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b165f540fe3c6280f1c6a7c2b4dec716a1fa611
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053096"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>インターネット接続でTeams 電話システムを確認する

Teams 電話システムは、Microsoft 365 クラウドを使用してMicrosoft Teams内で電話機能を有効にする Microsoft のテクノロジです。 Microsoft Teamsと電話システムを使用するすべてのデバイスには、インターネットへの接続が必要です。

最適な電話システムエクスペリエンスを実現するには、組織が一度に行う可能性がある最大通話数をサポートできるブロードバンド インターネット接続が必要です。 また、ネットワーク上のコンピューターがMicrosoft 365 サービスにアクセスできることを確認する必要もあります。

## <a name="check-your-internet-connection-speed"></a>インターネット接続速度を確認する

この記事は、インターネット接続が電話をかける必要があるユーザーの数に十分な速度であるかどうかを判断するのに役立ちます。 組織に関する情報を提供し、Teamsと電話システムで使用されるインターネット接続の量を示すレポートを取得します。

### <a name="gather-information-about-your-internet-connection-and-users"></a>インターネット接続とユーザーに関する情報を収集する

始める前に、次の情報が必要です。

* インターネット接続の速度
* 主にオフィスから電話システムを使用するユーザーの数
* 主にホーム オフィスなどの遠隔地から電話システムを使用するユーザーの数

### <a name="enter-your-information-into-the-network-planner"></a>ネットワーク プランナーに情報を入力する

次の手順を実行します。

1. ブラウザーで 、 [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com). グローバル管理者権限を持つアカウントを使用してサインインします。 Microsoft 365にサインアップするために使用したアカウントには、これらのアクセス許可があります。
2. **[計画]** を開いて **[ネットワーク プランナー]** を選択します。
3. **[ネットワーク プラン]** で、**[追加]** を選択します。 プランの名前を入力して、**[適用]** を選択します。
4. ネットワーク プランの名前を選択します。
5. 次のページで、**[ネットワーク サイト]** タブで **[ネットワーク サイトを追加]** を選択します。
6. **[ネットワーク サイト名**]、[**ネットワーク ユーザー]**、[**インターネット リンク容量**] の各フィールドに入力し、[保存] を選択 **します**。 この画面上の他のフィールドを空白のままにしておき、**[ExpressRoute]** も **[WAN に接続済み]** のオプションも選択しないでください。
7. **[レポート]** タブで、**[レポートの開始]** を選択します。
8. **レポート名** と **ネットワーク ユーザー** の数 (**Office** と **リモート**) を入力し、[**レポートの生成**] を選択して、Teamsの帯域幅要件を示すレポートを作成します。 次のセクションでレポートを読む方法について説明します。

### <a name="find-your-minimum-internet-connection-speed"></a>最小インターネット接続速度を確認する

[レポートの **生成**] を選択すると、レポートMicrosoft 365作成されます。

[**影響**] 列と **[Office 365**] 行の下に、インターネット接続のTeamsと電話システムの使用量が表示されます。 この数は、インターネット接続速度の合計の 30% 以下にすることをお勧めします。 たとえば、インターネット接続が *60 Mbps* の場合、Teamsと電話システムは *18 Mbps* 以下を使用する必要があります。

次の式を使用して、インターネット接続の最小速度を決定します。 *<影響数> / 0.3 です*。  

影響の数が *4.6875 Mbps* であるとします。 最小インターネット接続速度を調べる計算は *、4.6875 / 0.3 = 15.6 になります*。 この場合、インターネット接続速度は *15.6 Mbps 以上* である必要があります。

Teamsと電話システムでインターネット接続速度の合計の 30% を超える割合が使用される場合、**影響** の数は赤で表示されます。 その場合は、インターネット接続のアップグレードが必要になる場合があります。

![接続速度の警告。](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> Network Planner によって提供される帯域幅への影響は見積もりのみです。 [通話品質ダッシュボード](../cqd-what-is-call-quality-dashboard.md)を使用して、組織内のMicrosoft Teamsで音声通話とビデオ通話のユーザー エクスペリエンスを積極的に監視することをお勧めします。

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>ネットワーク上のコンピューターとデバイスが Microsoft 365 に到達できることを確認する

電話システムを使用するコンピューターとデバイスは、Microsoft 365 サービスと通信するために特定のネットワーク ポートを使用する必要があります。 これらのポートは、本質的に、デバイスがネットワークまたはインターネットを介して相互に通信するドアです。 ファイアウォールでは、次の *送信* ネットワーク ポートを使用して、ネットワーク上のデバイスが Microsoft 365 に到達できるようにする必要があります。

* **TCP ポート** 80 と 443
* **UDP ポート** 3478、3479、3480、3481

ファイアウォールでこれらのネットワーク ポートでの通信が許可されているかどうかを確認する最も簡単な方法は、テストするオフィスの場所から[Microsoft 365ネットワーク接続ツール](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool)を使用して接続テストを実行することです。 テストが完了したら、結果と推奨事項を確認します。
