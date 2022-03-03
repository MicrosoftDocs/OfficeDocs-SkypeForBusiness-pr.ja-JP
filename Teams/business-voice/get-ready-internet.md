---
title: インターネット接続で接続を確認Teams 電話システム
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
description: インターネットを使用する準備ができていることを確認Teams 電話システム
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b165f540fe3c6280f1c6a7c2b4dec716a1fa611
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053096"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>インターネット接続で接続を確認Teams 電話システム

Teams 電話システムは、クラウド内で電話機能を有効にするための Microsoft Microsoft TeamsテクノロジMicrosoft 365です。 デバイスとデバイスを使用Microsoft Teams、電話システムインターネットへの接続が必要です。

最適な電話システムするには、組織が一度に行う可能性がある電話の最大数をサポートできるブロードバンド インターネット接続が必要です。 また、ネットワーク上のコンピューターが他のサービスにアクセスMicrosoft 365があります。

## <a name="check-your-internet-connection-speed"></a>インターネット接続速度を確認する

この記事は、電話をかける必要があるユーザーの数に対してインターネット接続が十分に高速かどうかを判断するのに役立ちます。 組織に関する情報を提供し、ユーザーが使用するインターネット接続の量を示すレポートをTeams、電話システム。

### <a name="gather-information-about-your-internet-connection-and-users"></a>インターネット接続とユーザーに関する情報を収集する

始める前に、次の情報が必要です。

* インターネット接続の速度
* 主に自分のオフィスから電話システムユーザーの数
* 自宅オフィスなど、電話システムから使用するユーザーの数

### <a name="enter-your-information-into-the-network-planner"></a>ネットワーク プランナーに情報を入力する

次の手順を実行します。

1. ブラウザーで に移動します [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com)。 グローバル管理者権限を持つアカウントを使用してサインインします。 アカウントにサインアップするために使用したアカウントにはMicrosoft 365アクセス許可があります。
2. **[計画]** を開いて **[ネットワーク プランナー]** を選択します。
3. **[ネットワーク プラン]** で、**[追加]** を選択します。 プランの名前を入力して、**[適用]** を選択します。
4. ネットワーク プランの名前を選択します。
5. 次のページで、**[ネットワーク サイト]** タブで **[ネットワーク サイトを追加]** を選択します。
6. [ネットワーク サイト **名]、[****ネットワーク ユーザー]**、および [インターネット リンクの容量] フィールドに **入力** し、[保存] を選択 **します**。 この画面上の他のフィールドを空白のままにしておき、**[ExpressRoute]** も **[WAN に接続済み]** のオプションも選択しないでください。
7. **[レポート]** タブで、**[レポートの開始]** を選択します。
8. レポート名 **と** ネットワーク **ユーザー数 (****Office** とリモート) を入力し、[レポートの生成] を選択して、Teams の帯域幅要件を示すレポートを作成します。 次のセクションでレポートを読む方法について説明します。

### <a name="find-your-minimum-internet-connection-speed"></a>インターネット接続の最小速度を確認する

[レポートの生成 **] を選択** するとMicrosoft 365レポートが作成されます。

[**影響] 列** と [**Office 365] 行** に、使用するインターネット接続のTeamsと電話システム表示されます。 この数は、インターネット接続の合計速度の 30% 以下にすることをお勧めします。 たとえば、インターネット接続が *60 Mbps* の場合、Teamsと電話システム *18 Mbps 以下を使用する必要があります*。

次の数式を使用して、インターネット接続の最小速度を決定します。<*影響>/ 0.3*。  

影響の数が *4.6875 Mbps とします*。 インターネット接続の最小速度を確認する計算は *、4.6875 / 0.3 = 15.6 です*。 この場合、インターネット接続速度は *15.6 Mbps 以上である必要があります*。

すべてのTeams、電話システムインターネット接続速度の 30% を超える割合を使用する場合、[影響] の **数は赤** で表示されます。 その場合は、インターネット接続のアップグレードが必要な場合があります。

![接続速度の警告。](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> Network Planner によって提供される帯域幅への影響は見積もりのみです。 通話品質ダッシュボード[を使用して](../cqd-what-is-call-quality-dashboard.md)、組織内の音声通話とビデオ通話のユーザー エクスペリエンスをMicrosoft Teamsをお勧めします。

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>ネットワーク上のコンピューターとデバイスが Microsoft 365 に到達できることを確認する

デバイスを使用するコンピューター電話システム、特定のネットワーク ポートを使用して、サービスと通信Microsoft 365があります。 これらのポートは、基本的に、ネットワークまたはインターネット経由でデバイスが互いに通信するドアです。 ファイアウォールでは、次の *送信* ネットワーク ポートを使用して、ネットワーク上のデバイスが Microsoft 365 に到達できるようにする必要があります。

* **TCP ポート** 80 と 443
* **UDP ポート** 3478、3479、3480、3481

これらのネットワーク ポートでファイアウォールが通信を許可するかどうかを確認する最も簡単な方法は、テストするオフィスの場所から [Microsoft 365 ネットワーク](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool)接続ツールを使用して接続テストを実行する方法です。 テストを完了した後、結果と推奨事項を確認します。
