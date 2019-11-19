---
title: インターネット接続を確認する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653553"
---
# <a name="check-your-internet-connection"></a>インターネット接続を確認する

Business Voice は、Microsoft 365 のクラウドにあります。 Microsoft Teams および Business Voice を使用するすべてのコンピューターとデバイスで、インターネット接続が必要になります。 Business Voice を最大限に活用するには、予想される電話の数を一度にサポートできるブロードバンド インターネット接続が必要です。 また、ネットワーク上のコンピューターが Microsoft 365 サーバーに到達できることを確認する必要もあります。

これらの手順を実行するには、次のいずれかのサブスクリプションを持つテナントが必要です。

* Office 365 Business Essentials
* Office 365 Business Premium
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 Business

これらの手順を実行するのに Business Voice ライセンスは必要ありません。

## <a name="check-your-internet-connection-speed"></a>インターネット接続の速度を確認する

この記事は、電話をかける必要のある人数、ビデオ会議のホストなどに対応するのにインターネット接続が十分な速度であるかどうかを判断するのに役立ちます。 組織に関する情報を入力すると、Teams や Business Voice で使用されるインターネット接続の量が記載されたレポートが返されます。

### <a name="get-information-about-your-internet-connection-and-users"></a>インターネット接続とユーザーに関する情報を入手する

始める前に、次の情報を知っておく必要があります。

* インターネット接続の速度。
* 主にオフィス内で Business Voice を使用する人数。
* ホーム オフィスなど、主にリモートの場所で Business Voice を使用する人数。

### <a name="enter-your-information-into-the-network-planner"></a>ネットワーク プランナーに情報を入力する

必要な操作は次のとおりです。

1. ブラウザーを開き、https://admin.teams.microsoft.com に移動して、グローバル管理者のアクセス許可を持つアカウントでサインインします。 Office 365 へのサインアップに使用したアカウントには、これらのアクセス許可があります。
1. **[計画]** を開いて **[ネットワーク プランナー]** を選択します。
1. **[ネットワーク プラン]** で、**[追加]** を選択します。 プランの名前を指定して、**[適用]** を選択します。 ネットワーク プランは次のようになります。

    ![ネットワーク プランナーのメイン画面](../media/network-planner-main.png)
1. ネットワーク プランの名前をクリックします (上の図の**本社**)。
1. 次のページで、**[ネットワーク サイト]** タブの **[ネットワーク サイトを追加]** を選択します。
1. 以下のスクリーンショットに示されているフィールドにのみ入力し、**[保存]** を選択します。 この画面上の他のフィールドを空白のままにしておき、**[ExpressRoute]** も **[WAN に接続済み]** のオプションも選択しないでください。

    ![ネットワーク プランナー サイトに関する情報](../media/network-planner-site-info.png)
1. **[レポート]** タブで、**[レポートの開始]** を選択します。
1. 次の情報を入力してから **[レポートの生成]** を選択し、Teams の帯域幅要件を示すレポートを作成します。 次のセクションでは、レポートを読み込む方法について説明します。

    ![ネットワーク プランナー レポートに関する情報](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>インターネット接続の最低速度を確認する

**[レポートの生成]** を選択すると、Office 365 で次のようなレポートが作成されます。

![ネットワーク プランナー レポートの詳細](../media/network-planner-report.png)

強調表示された数値は、Teams と Business Voice で使用するインターネット接続の量を示しています。 この数値が、インターネット接続の合計速度の 30% を超えないようにすることをお勧めします。 たとえば、インターネット接続が 60 Mbps の場合、Teams や Business Voice は 18 Mbps を超えないようにする必要があります。

インターネット接続の最低速度を確認するには、次の計算を行います。`<highlighted number> / .3`。 上の図で強調表示された数値を使用すると、`4.6875 / .3 = 15.6` になります。 つまり、インターネット接続の最低速度は、少なくとも 15.6 Mbps である必要があります。

Teams と Business Voice での使用量がインターネット接続の合計速度の 30% を超える場合、強調表示された数値が赤色で表示されます。 この場合、インターネット接続をアップグレードする必要がある場合があります。

![接続速度の警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>ネットワーク上のコンピューターとデバイスが Microsoft 365 に到達できることを確認する

正常に動作させるには、Business Voice で使用するコンピューターとデバイスが特定のネットワーク ポートを使用して Microsoft 365 サーバーと通信する必要があります。 ネットワーク ポートは実質的に、ネットワークやインターネット経由でコンピューターとデバイスが相互に通信するための出入口です。 ファイアウォールでは、次の送信ネットワーク ポートを使用して、ネットワーク上のコンピューターとデバイスが Microsoft 365 に到達できるようにする必要があります。

* **TCP ポート** 80 と 443
* **UDP ポート** 3478、3479、3480、3481

お使いのファイアウォールでこれらのネットワーク ポート上の通信が許可されているかどうかを確認する一番簡単な方法は、Teams を使用してテスト通話を行うことです。 テスト通話を行うには、次の操作を行います。

1. ネットワーク上のコンピューターで https://aka.ms/getteams に移動して、Teams をインストールします。 スピーカーとマイクがこのコンピューターに接続されていることを確認します。
2. Teams を開いて、Microsoft 365 アカウントを使用してサインインします
3. Teams で、プロファイルの画像を選択してから、**[設定]**  >  **[デバイス]** の順に選択します
4. **[オーディオ デバイス]** の **[テスト通話]** を選択します
5. プロンプトに従ってメッセージを残し、メッセージを再生します

* 電話が繋がり、メッセージを再生できたら、ファイアウォールは正しく設定されています。
* 電話は繋がるものの、プロンプトが聞こえない場合またはメッセージが再生されない場合は、コンピューターによってスピーカーとマイクが正しく設定され、検出されていることを確認します。 もう一度お試しください。
* 電話が繋がらない場合、または繋がるもののメッセージが聞こえない場合は、ファイアウォールを更新して、上のリストに表示されているネットワーク ポートを許可する必要がある場合があります。 ネットワーク ポートがインターネットに到達できるようにする方法については、ファイアウォールのドキュメントを確認するか、IT スペシャリストにお問い合わせください。

IT プロフェッショナルで、Business Voice をサポートするためにより大きくて複雑なネットワークを準備する方法の詳細が必要な場合は、「[環境を評価する](../3-envision-evaluate-my-environment.md)」をご覧ください。 記事「[環境を評価する](../3-envision-evaluate-my-environment.md)」では、帯域幅、プロキシ、ファイアウォールの要件に関する詳細と、[Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) を使用してネットワークをテストする方法について説明します。
