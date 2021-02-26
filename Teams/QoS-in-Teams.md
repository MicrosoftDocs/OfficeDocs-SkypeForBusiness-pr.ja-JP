---
title: Microsoft Teams でサービス品質を実装する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft Teams でサービス品質 (QoS) を実装するために組織のネットワークを準備する方法を説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766580"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Microsoft Teams でサービス品質 (QoS) を実装する

Microsoft Teams でサービス品質 (QoS) を使用すると、ネットワークの遅延の影響を受けやすいリアルタイムのネットワーク トラフィック (音声ストリームやビデオストリームなど) が、影響を受けにくいトラフィック (新しいアプリのダウンロードなど。ダウンロードに数秒長くかかることは大きな問題ではありません) の前に "横入り" できるようになります。 QoS は、Windows グループ ポリシー オブジェクトとポートベースのアクセス制御リストを使用して、リアルタイム ストリーム内のすべてのパケットを識別してマークします。 これは、ネットワークが音声、ビデオ、および画面共有ストリームにネットワーク帯域幅の専用の部分を提供するのに役立ちます。

この記事で説明する問題のいずれかが発生している大規模なグループ ユーザーをサポートする場合は、QoS を実装する必要がある可能性があります。 ユーザー数が少ない小規模企業では、QoS を必要としない場合がありますが、それらの企業においても役立つことがあります。

何らかの形で QoS を使用しないと、音声とビデオで以下のような品質上の問題が生じる可能性があります。

- ジッター – メディア パケットが異なるレートで到着すると、通話で語や音節が欠落する可能性があります
- パケット損失 – パケットが脱落すると、音声品質が低下したり、音声の理解が困難になったりすることがあります
- ラウンド トリップ時間 (RTT) の遅延 – メディア パケットが宛先に到達するのに長い時間がかかります。それにより、会話する二者間で顕著な遅延が生じ、両者が同時に話す現象を引き起こします

これらの問題に対処する最も簡単な方法は、内部とインターネットへの出力の両方でデータ接続のサイズを増やすことです。 その方法は多大なコストがかかることが多いため、QoS では、帯域幅を追加する代わりに、所有しているリソースをより効果的に管理する方法を提供します。 品質の問題に対処するには、最初に QoS を使用してから、必要な場合にのみ帯域幅を追加することをお勧めします。

QoS を有効にするには、組織全体に一貫性のある QoS 設定を適用する必要があります。 QoS の優先順位をサポートできないパスの部分では、通話、ビデオ、および画面共有の品質が低下する可能性があります。 これには、すべてのユーザーの PC、デバイス、ネットワーク スイッチ、インターネットへのルーター、および Teams サービスに対する設定の適用が含まれます。

_図 1. 組織のネットワークと Microsoft 365 または Office 365 サービス間の関係_

![ネットワークとサービスの関係を示す図](media/Qos-in-Teams-Image1.png "組織のネットワークと Microsoft 365 および Office 365 サービスの間の関係: オンプレミスのネットワークとデバイスは、相互接続ネットワークに接続します。相互接続ネットワークは、Microsoft 365 および Office 365 のクラウド ボイスと電話会議のサービスに接続します。")

## <a name="qos-implementation-checklist"></a>QoS の実装のチェックリスト

上位レベルでは、QoS を実装するために以下のことを行います。

1. [ネットワークの準備ができていることを確認する](#make-sure-your-network-is-ready)

1. [QoS の実装方法を選択する](#select-a-qos-implementation-method)

1. [各メディア タイプの初期ポート範囲を選択する](#choose-initial-port-ranges-for-each-media-type)

1. 以下のように QoS 設定を実装する:
   1. クライアントでグループ ポリシー オブジェクト (GPO) を使用して、[クライアント デバイスのポート範囲とマーキングを設定](QoS-in-Teams-clients.md)します。
   2. ルーター (製造元の資料を参照) または他のネットワーク デバイスで実装します。 これには、ポートベースのアクセス制御リスト (ACL) を含めるか、単に QoS キューと DSCP マーキングを定義するか、またはこれらすべてを含めることもできます。

      > [!IMPORTANT]
      > これらの QoS ポリシーは、クライアントの送信元ポートと、送信元と宛先の IP アドレスを "any"として実装することをお勧めします。 これにより、内部ネットワーク上の受信と送信の両方のメディア トラフィックがキャッチされます。  

   3. [Teams 会議のメディア トラフィックの処理方法を設定する](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. ネットワーク上の Teams トラフィックを分析して [QoS 実装を検証](#validate-your-qos-implementation)します。

QoS の実装を準備する際には、次のガイドラインに留意してください。

- Microsoft 365 への最短パスが最適です
- ポートを閉じると品質が低下します
- プロキシなどの障害となるものは推奨されません
- ポップ数を制限します:
  - クライアントからネットワーク エッジ - 3 から 5 ホップ
  - ISP から Microsoft ネットワーク エッジ - 3 ホップ
  - Microsoft ネットワーク エッジから最終目的地 - 無関係

ファイアウォールのポートの構成については、「[Office 365 の URL と IP 範囲](office-365-urls-ip-address-ranges.md)」をご覧ください。

## <a name="make-sure-your-network-is-ready"></a>ネットワークの準備ができていることを確認する

QoS の実装を検討している場合、帯域幅の要件と他の[ネットワーク要件](prepare-network.md)が既に特定されている必要があります。
  
ネットワーク全体のトラフィックの輻輳は、メディアの品質に大きく影響します。 帯域幅が不足すると、パフォーマンスが低下し、ユーザー エクスペリエンスの品質低下につながります。 Teams を導入し、使用量が増えたときに、レポート、[ユーザーごとの通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)、[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md)を使用して問題を特定し、QoS と追加の選択的な帯域幅を使用して調整を行います。

### <a name="vpn-considerations"></a>VPN に関する考慮事項

QoS が期待どおりに機能するのは、発信者間のすべてのリンクで実装されている場合のみです。 内部ネットワークで QoS を使用しているときにユーザーがリモートの場所からサインインする場合、管理された内部ネットワーク内でのみ優先順位付けをすることができます。 リモートの場所でも仮想プライベート ネットワーク (VPN) を実装することによって管理された接続を受信できますが、VPN では本質的にパケットにオーバーヘッドが追加されるので、リアルタイムのトラフィックに遅延が生じます。 VPN を使用したリアルタイム通信トラフィックの実行は避けることをお勧めしています。

大陸間で管理されたリンクを使用するグローバル組織では、そのようなリンクの帯域幅は LAN と比較して制限されるため QoS を強く推奨します。

## <a name="introduction-to-qos-queues"></a>QoS キューの概要

QoS を提供するには、ネットワーク デバイスでトラフィックを分類する手段が必要であり、他のネットワーク トラフィックから音声やビデオを区別できなければなりません。

ネットワーク トラフィックがルーターに入ったら、トラフィックはキューに入れられます。 QoS ポリシーが構成されていない場合、1 つのキューのみが存在し、すべてのデータは同じ優先順位を持ち、先入先出法で処理されます。 これは、遅延に極めて敏感な音声トラフィックが、数ミリ秒の遅延があっても問題とならないトラフィックにはさまれる可能性があることを意味します。

QoS を実装するときは、Cisco のプライオリティ キューイングや [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) などの輻輳管理機能のいずれかと、[重み付けランダム早期検出 (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection):などの輻輳回避機能を使用して、複数のキューを定義します。

_図 2. QoS キューの例_

![QoS キューと帯域幅分割の図](media/Qos-in-Teams-Image2.png "使用可能な合計帯域幅は、複数のキュー (オーディオ、ビデオ、その他のトラフィック) で分割されます。それらには、それぞれ異なる優先順位が割り当てられています。")

わかりやすく例えると、QoS ではデータ ネットワークに仮想の "相乗り車線" を作成して、一部の種類のデータでは遅延がまったく生じない、またはほとんど生じないようにすることができます。 そのような車線を作成すると、組織ユーザーに提供するビジネス水準のエクスペリエンスを維持しながら、それらの車線の相対的なサイズを調整して、保有している接続帯域幅をより有効に管理できるようになります。

## <a name="select-a-qos-implementation-method"></a>QoS 実装方法を選択する

ネットワーク ルーターでアクセス制御リスト (ACL) を使用して、ポートベースのタグ付けによって QoS を実装できます。 ポートベースのタグ付けは、Windows、Mac、Linux が混在する環境で機能し、最も簡単に実装できることから、最も信頼性が高い方法といえます。 モバイル クライアントでは、DSCP 値を使用してトラフィックをマークするメカニズムが提供されないため、この方法が必要になります。  

ポートベースのタグ付けを使用すると、ネットワーク ルーターが受信パケットを検査します。パケットが特定のポートまたはポート範囲を使用して到着すると、そのパケットは特定の種類のメディアとして識別されて該当する種類のキューに置かれます。その際、事前に定義された [DSCP](https://tools.ietf.org/html/rfc2474) マークが IP パケットのヘッダーに追加されます。これにより、他のデバイスはそのトラフィックの種類を認識して、キュー内で優先順位を付けられるようになります。

ポートベースのタグ付けは異なるプラットフォーム間で機能しますが、クライアント マシンに到達するまでの経路全体ではなく、WAN エッジにおいてのみトラフィックがマークされるため、管理のオーバーヘッドが生じます。 この方法の実装手順については、ルーターの製造元から提供されたドキュメントを参照してください。

### <a name="insert-dscp-markers"></a>DSCP マーカーを挿入する

グループ ポリシー オブジェクト (GPO) を使用して QoS をクライアント デバイスに直接実装し、特定の種類のトラフィック (音声など) であることを示す DSCP マーカーを IP パケットのヘッダーに挿入することもできます。 ルーターとその他のネットワーク デバイスでは、これらのマーキングを認識し、トラフィックを優先度の高い個別のキューに配置するように構成できます。

このシナリオ全体は有効ですが、ドメインに参加している Windows クライアントでのみ機能します。 ドメインに参加している Windows クライアントではないデバイスでは、DSCP タグ付けが有効になりません。 Mac OS などのクライアントでは、ハードコードされたタグがあり、常にトラフィックがタグ付けされます。

利点としては、GPO を介して DSCP マーキングを制御することで、ドメインに参加しているすべてのコンピューターが同じ設定を受信し、管理者だけがそれを管理できるようになります。 GPO を使用できるクライアントは、元のデバイスでタグ付けされ、構成されたネットワーク デバイスでは DSCP コードによってリアルタイム ストリームを認識して、適切な優先順位を付けることができます。

### <a name="best-practice"></a>ベスト プラクティス

可能であれば、エンドポイントでの DSCP マーキングと、ルーターでのポートベースの ACL を組み合わせて使用することをお勧めします。 グループ ポリシー オブジェクトを使用して大部分のクライアントに対応し、同時にポートベースの DSCP タグ付けを使用すると、モバイル、Mac、その他のクライアントも (少なくとも部分的には) QoS の対象にすることができます。

DSCP マーキングは、郵便仕分けで押されるスタンプに例えることができます。スタンプによって、配達の緊急性と、迅速な配達を行うためにそれを分類する最善の方法が示されます。 リアルタイム メディア ストリームに優先順位を付けるようにネットワークを構成すると、パケットの損失とパケットの遅延が大幅に減少します。

ネットワーク内のすべてのデバイスで同じ分類、マーキング、優先順位が使用されるようにすると、各トラフィックの種類で使用されるキューに割り当てられたポート範囲のサイズを変更することで、遅延、パケットの損失、ジッターを低減または排除することができます。 Teams の観点からすると、最も重要な構成の手順は、パケットの分類とマーキングです。 ただし、エンドツーエンドの QoS を成功させるには、アプリケーションの構成を基盤となるネットワークの構成に慎重に合わせる必要もあります。 QoS が完全に実装された後は、組織のニーズと実際の使用状況に基づいて、各トラフィックの種類に割り当てられたポート範囲を調整することが、継続的な管理上の課題となります。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>各メディア タイプ用の初期ポート範囲を選択する

DSCP 値は、パケットまたはストリームに与える優先順位と、DSCP マークがクライアントによって割り当てられているか、または ACL 設定に基づいてネットワーク自体によって割り当てられているかを、対応するように構成されたネットワークに示します。 各メディアのワークロードには、固有の DSCP 値 (他のサービスでは DSCP マーキングの共有が許可されることがありますが、Teams では許可されません) と、各メディアの種類で使用される定義済みの個別のポート範囲が与えられます。 他の環境には既存の QoS 戦略がある場合があります。それは、ネットワーク ワークロードの優先順位を決定するのに役立ちます。

各種のリアルタイム ストリーミング ワークロードのポート範囲の相対サイズによって、対象ワークロードが独占的に使用できる合計帯域幅のうちの比率が決まります。 前述の郵便仕分けの例えに戻ると、"Air Mail" のスタンプが押された手紙は最寄りの空港まで 1 時間以内に到着する可能性がありますが、"大口郵便" とマークされた小包は何台ものトラックで陸送されるまでに 1 日待機する可能性があります。

_推奨される初期ポート範囲_

|メディア トラフィックの種類| クライアントの送信元ポート範囲 |プロトコル|DSCP 値|DSCP クラス|
|:--- |:--- |:--- |:--- |:--- |
|オーディオ| 50,000–50,019|TCP/UDP|46|完全優先転送 (EF)|
|ビデオ| 50,020–50,039|TCP/UDP|34|相対的優先転送 (AF41)|
|アプリケーション/画面共有| 50,040–50,059|TCP/UDP|18|相対的優先転送 (AF21)|
||||||

これらの設定を使用する場合は、以下の点に注意してください。

- 将来 ExpressRoute を実装する予定で、まだ QoS を実装していない場合は、ガイダンスに従って、DSCP値が送信者と受信者間で同じになるようにすることをお勧めします。
- モバイル クライアントや Teams デバイスを含むすべてのクライアントは、これらのポート範囲を使用し、これらの送信元ポート範囲を使用して実装するすべての DSCP ポリシーの影響を受けます。 動的ポートを引き続き使用するクライアントは、ブラウザーベースのクライアント (参加者を各自のブラウザーを使用して会議に参加させるクライアント) のみです。
- Mac クライアントは同じポート範囲を使用しますが、オーディオ (EF) とビデオ (AF41) のハードコードされた値も使用します。 これらの値を構成することはできません。
- ユーザー エクスペリエンスを向上させるために、後でポート範囲を調整する必要がある場合は、ポート範囲が重なることなく、相互に隣接するようにする必要があります。

## <a name="migrate-qos-to-teams"></a>QoS を Teams に移行する

以前に Skype for Business Online を展開したことがあり (QoS のタグ付けやポート範囲を含む)、現在  Teams を展開している場合は、Teams は既存の構成を優先して、Skype for Business クライアントと同じポート範囲とタグ付けを使用します。 ほとんどの場合、追加の構成は必要ありません。

> [!NOTE]
> グループ ポリシーによってアプリケーション名の QoS タグ付けを使用している場合は、アプリケーション名として Teams.exe を追加する必要があります。

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>PowerShell を使用して Windows 上の Teams に QoS を実装する

**オーディオ用に QoS を設定する**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**ビデオ用に QoS を設定する**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**共有用に QoS を設定する**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Teams 管理センターで送信元ポートを管理する

Teams では、さまざまなワークロードで使用される QoS の送信元ポートをアクティブに管理し、必要に応じて調整する必要があります。 「[各メディアの種類用の初期ポート範囲を選択する](#choose-initial-port-ranges-for-each-media-type)」の表に記されているように、ポート範囲は調整できますが、DSCP マーキングを構成することはできません。 これらの設定を実装した後で、特定のメディアの種類に必要なポート数が現状よりも多い (または、少ない) ことが判明する場合があります。 Teams の実装後、[ユーザーごとの通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)と[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md)を使用して、ポート範囲の調整を決定し、ニーズの変化に応じて定期的に変更する必要があります。

> [!NOTE]
> Skype for Business Online 用の送信元ポート範囲と DSCP マーキングに基づいて QoS を既に構成済みの場合には、同じ構成が Teams に適用され、マッピングに対するクライアントやネットワークの変更は必要ありません。ただし、Skype for Business Online で構成された内容と一致させるために、[Teams で使用する範囲を設定](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)しなければならない場合があります。

以前にオンプレミスの Skype for Business Server を展開したことがある場合は、QoS ポリシーを再調査しなければならない場合があります。 確認したポート範囲の設定に一致するようにポリシーを調整して、Teams に質の高いユーザー エクスペリエンスを提供します。

## <a name="validate-your-qos-implementation"></a>QoS の実装を検証する

QoS を有効にするには、GPO によって設定された DSCP 値が、通話の両端に存在する必要があります。 Teams クライアントによって生成されたトラフィックを分析することで、Teams のワークロード トラフィックがネットワーク内を移動するときに、DSCP 値が変更、または削除されていないことを確認できます。

可能であれば、ネットワークの出口ポイントでトラフィックをキャプチャします。 スイッチやルーターでポート ミラーリングを使用して、この問題を解決できます。

## <a name="implement-qos-for-other-devices"></a>他のデバイスに QoS を実装する

Intune、Surface、iOS、Android、Mac の QoS の実装については、次のトピックを参照してください。

- [Surface Hub 2S の QoS](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [Surface Hub の QoS](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [iOS、Android、Mac の QoS](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>関連トピック

- [ビデオ: ネットワークの計画](https://aka.ms/teams-networking)

- [Microsoft Teams 用に組織のネットワークを準備する](prepare-network.md)

- [Teams クライアント に QoS を実装する](QoS-in-Teams-clients.md)
