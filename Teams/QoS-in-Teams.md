---
title: Microsoft Teams でサービスの品質 (QoS) を実施する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft Teams でサービスの品質 (QoS) のために組織のネットワークを準備する方法について説明します。
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766580"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Microsoft Teams でサービスの品質 (QoS) を実装する

Microsoft Teams の QoS (Quality of Service) では、ネットワークの遅延 (音声やビデオのストリームなど) に影響を受けているリアルタイムのネットワークトラフィックが、機密性の低いトラフィック (たとえば、新しいアプリをダウンロードしても、追加のもう1つ目のダウンロードは大きなものではありません) になります。 QoS では、Windows のグループポリシーオブジェクトとポートベースのアクセス制御リストを使用して、リアルタイムストリーム内のすべてのパケットを特定してマークします。 これにより、ネットワークがネットワーク帯域幅の専用部分を使って、音声、ビデオ、画面共有を行うことができます。

この記事で説明されているいずれかの問題が発生している大規模なユーザーをサポートしている場合は、おそらく QoS を実装する必要があります。 ユーザー数の少ない小規模企業は、QoS を必要としない場合もありますが、役に立ちます。

QoS の形式がないと、音声とビデオで次の品質の問題が発生する可能性があります。

- ジッター–さまざまな料金で受信するメディアパケット。通話に単語または音節が含まれていない可能性があります。
- パケット損失–パケットが破棄されると、音声品質が低下し、音声認識が困難になることもあります。
- 遅延したラウンドトリップ時間 (RTT) –メディアパケットが相手に届くまでに時間がかかります。これにより、会話中に2つの当事者間で顕著な遅延が発生し、ユーザーが互いに連絡を取り合うようになります。

これらの問題に対処するための最も複雑な方法は、内部とインターネットの両方でデータ接続のサイズを大きくすることです。 多くの場合、費用がかかる場合があるため、QoS は帯域幅を追加する代わりに、使用しているリソースをより効果的に管理する手段となります。 品質の問題を解決するには、最初に QoS を使用し、必要に応じて帯域幅のみを追加することをお勧めします。

QoS を有効にするには、組織全体で一貫した QoS 設定を適用する必要があります。 QoS の優先順位をサポートしていないパスの部分は、通話、ビデオ、画面共有の品質を低下させる可能性があります。 これには、すべてのユーザーの Pc またはデバイス、ネットワークスイッチ、インターネットへのルーター、および Teams サービスへの設定の適用が含まれます。

_図1組織のネットワークと Microsoft 365 または Office 365 サービスの間の関係_

![ネットワークとサービス間の関係を示す図](media/Qos-in-Teams-Image1.png "組織のネットワークと Microsoft 365 または Office 365 サービスの間の関係: オンプレミスのネットワークとデバイスは、相互接続ネットワークに接続されます。これは、Microsoft 365 または Office 365 クラウドの音声と電話会議サービスに接続します。")

## <a name="qos-implementation-checklist"></a>QoS の実装のチェックリスト

高レベルでは、次の操作を実行して QoS を実装します。

1. [ネットワークの準備ができていることを確認する](#make-sure-your-network-is-ready)

1. [QoS の実装方法を選択する](#select-a-qos-implementation-method)

1. [各メディアの種類の初期ポート範囲を選ぶ](#choose-initial-port-ranges-for-each-media-type)

1. QoS 設定を実装します。
   1. グループポリシーオブジェクト (GPO) を使用するクライアントで、[クライアントデバイスのポート範囲とマークを設定](QoS-in-Teams-clients.md)する
   2. ルーター (製造元のマニュアルを参照)、または他のネットワークデバイスを参照してください。 これには、ポートベースのアクセス制御リスト (Acl) が含まれていることもあれば、QoS キューと DSCP マーキングのいずれかを定義することもあります。

      > [!IMPORTANT]
      > これらの QoS ポリシーは、クライアントソースポートと、発信元と送信先の IP アドレスを "any" として実装することをお勧めします。 これにより、内部ネットワーク上の受信および送信メディアの両方のトラフィックがキャッチされます。  

   3. [Teams 会議でメディアトラフィックを処理する方法を設定する](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. ネットワーク上のチームトラフィックを分析して、 [QoS の実装を検証](#validate-your-qos-implementation)します。

QoS を実装する準備ができたら、次のガイドラインを念頭に置いてください。

- Microsoft 365 への最短パス
- ポートを閉じると音質が低下する
- プロキシなどの障害物はお勧めしません。
- ホップ数を制限します。
  - クライアントからネットワークエッジへ-3 ~ 5 ホップ
  - ISP から Microsoft ネットワークエッジ–3ホップ
  - Microsoft ネットワークエッジから最終的な送信先への関連性がない

ファイアウォールのポートを構成する方法については、「 [Office 365 の URL と IP 範囲](office-365-urls-ip-address-ranges.md)」をご覧ください。

## <a name="make-sure-your-network-is-ready"></a>ネットワークの準備ができていることを確認する

QoS の実装を検討している場合は、帯域幅要件とその他の [ネットワーク要件](prepare-network.md)を既に決定しておく必要があります。
  
ネットワーク全体でのトラフィック渋滞は、メディアの品質に大きく影響します。 帯域幅の不足は、パフォーマンスの低下を招き、ユーザーエクスペリエンスが低下します。 Teams の導入と使用量が増加するにつれて、レポート作成、 [ユーザーごとの通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)、 [通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md) を使用して問題を特定し、QoS と選択的な帯域幅の追加機能を使って調整を行います。

### <a name="vpn-considerations"></a>VPN に関する考慮事項

QoS は、呼び出し元間のすべてのリンクに実装されている場合にのみ動作します。 内部ネットワークで QoS を使用していて、ユーザーが遠隔地からサインインしている場合は、内部の管理されたネットワーク内でのみ優先順位を付けることができます。 リモートの場所は仮想プライベートネットワーク (VPN) を実装することによって管理された接続を受け取ることができますが、VPN の本質的にはパケットのオーバーヘッドが追加され、リアルタイムトラフィックで遅延が発生します。 VPN 経由のリアルタイム通信トラフィックを実行しないようにすることをお勧めします。

世界中の管理されたリンクを含むグローバル組織では、これらのリンクの帯域幅が LAN と比較して制限されているため、QoS を強くお勧めします。

## <a name="introduction-to-qos-queues"></a>QoS キューの概要

QoS を提供するには、ネットワークデバイスがトラフィックを分類するための手段を持っている必要があります。また、音声やビデオを他のネットワークトラフィックと区別できなければなりません。

ネットワークトラフィックがルーターに入ったら、トラフィックはキューに入れられます。 QoS ポリシーが構成されていない場合は、1つのキューしかありません。すべてのデータは、同じ優先度で最初のデータとして扱われます。 つまり、ボイストラフィック (遅延に非常に敏感) は、わずか数秒の遅延が問題となるトラフィックが遅れている可能性があります。

QoS を実装する場合、複数のキューを定義するには、Cisco の優先度キューや [クラスベースの加重公平なキュー (cbの](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 場合) や輻輳回避機能 ( [wred)](https://en.wikipedia.org/wiki/Weighted_random_early_detection)などの輻輳回避機能のいずれかを使用します。

_図2QoS キューの例_

![QoS キューと帯域幅区分の図](media/Qos-in-Teams-Image2.png "利用可能な帯域幅の合計は、複数のキュー (オーディオ、ビデオ、その他のトラフィック) で分割されます。これには、さまざまな優先順位が割り当てられています。")

簡単な例としては、QoS によってデータネットワーク内に仮想 "相乗りレーン" が作成されるため、データの種類によっては遅延が発生しないことがあります。 これらのレーンを作成した後は、組織のユーザーに対してビジネスレベルのエクスペリエンスを提供しながら、相対的なサイズを調整して、より効率的に接続の帯域幅を管理することができます。

## <a name="select-a-qos-implementation-method"></a>QoS の実装方法を選択する

ネットワークのルーターでアクセス制御リスト (Acl) を使用して、ポートベースのタグを使って QoS を実装することができます。 ポートベースのタグ付けは、Windows、Mac、および Linux の混合環境で動作するため、最も信頼できる方法です。 モバイルクライアントでは、DSCP 値を使ってトラフィックをマークするメカニズムは用意されていないため、このメソッドが必要になります。  

ポートベースのタグ付けを使用すると、ネットワークのルーターは受信パケットを調べます。また、特定のポートまたはポートの範囲を使ってパケットが着信した場合は、特定のメディアの種類として識別[DSCP](https://tools.ietf.org/html/rfc2474)し、それをその種類のキューに入れて、他のデバイスがそのトラフィックの種類を認識してキューの優先順位を上げる

ポートベースのタグ付けはプラットフォーム間で動作しますが、WAN edge でトラフィックをマークするだけで、管理のオーバーヘッドが生じます。 この方法を実装する手順については、ルーター製造元から提供されているドキュメントを参照してください。

### <a name="insert-dscp-markers"></a>DSCP マーカーを挿入する

また、グループポリシーオブジェクト (GPO) を使ってクライアントデバイスが、特定の種類のトラフィック (ボイスなど) であることを示す DSCP マーカーを IP パケットヘッダーに挿入することで、QoS を実装することもできます。 ルーターなどのネットワークデバイスでは、これを認識して、トラフィックを個別の優先度の高いキューに配置するように構成することができます。

このシナリオは完全に有効ですが、ドメインに参加している Windows クライアントに対してのみ機能します。 ドメインに参加していないデバイスでは、DSCP タグ付けは有効になりません。 Mac OS などのクライアントでは、ハードコーディングされたタグがあり、常にトラフィックがタグ付けされます。

正側では、GPO を使用して DSCP マーキングを制御することで、ドメインに参加しているすべてのコンピューターが同じ設定を受け取り、管理者だけがそれらを管理できるようになります。 GPO を使うことができるクライアントは、元のデバイスでタグ付けされ、設定されたネットワークデバイスでは、DSCP コードによってリアルタイムストリームを認識し、適切な優先順位を付けることができます。

### <a name="best-practice"></a>ベストプラクティス

可能であれば、エンドポイントとポートベースの Acl での DSCP マーキングをルーターで組み合わせることをお勧めします。 GPO を使用してほとんどのクライアントをキャッチし、さらにポートベースの DSCP タグを使用することで、モバイル、Mac、およびその他のクライアントでも QoS 処理を行うことができます (少なくとも一部)。

[DSCP マーキング] は、likened が配信されるまでの時間と、迅速な配信のために最適な並べ替えを行うことができるようにする郵送の頻度を示す切手にすることができます。 リアルタイムメディアストリームに優先順位を設定するようにネットワークを構成すると、紛失したパケットや遅延したパケットが大幅に減少します。

ネットワーク内のすべてのデバイスが同じ分類、マーキング、優先順位を使用している場合は、各トラフィックの種類で使用されるキューに割り当てられているポート範囲のサイズを変更することによって、遅延、破棄されたパケット、ジッタを削減または除去することができます。 Teams の観点から見ると、最も重要な構成手順は、パケットを分類してマークすることです。 ただし、エンドツーエンドの QoS を成功させるには、基になるネットワーク構成にアプリケーションの構成を慎重に合わせる必要があります。 QoS が完全に実装されたら、継続的な管理は、組織のニーズと実際の使用状況に基づいて、各トラフィックの種類に割り当てられたポート範囲を調整することになります。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>各メディアの種類の初期ポート範囲を選ぶ

DSCP 値は、対応して構成されたネットワークに、パケットまたはストリームを割り当てるための優先順位を示します。 DSCP マークがクライアントとネットワーク自体のどちらで割り当てられているかは、ACL 設定に基づいて判断されます。 メディアの各ワークロードには、独自の固有の DSCP 値が与えられます (他のサービスによっては、ワークロードで DSCP マーキング、チームにはない)、および各メディアの種類に対して定義され、個別のポート範囲を共有できます。 その他の環境には既存の QoS 戦略がある場合があります。これは、ネットワークワークロードの優先順位を決定するのに役立ちます。

さまざまなリアルタイムストリーミングワークロードのポート範囲の相対サイズによって、そのワークロード専用の使用可能な帯域幅の合計の比率が設定されます。 以前のお客様に戻るには、"Air Mail" スタンプ付きの文字が、最も近い空港から1時間以内に実行されることがあります。また、"一括メール" マークとマークされた小さいパッケージでは、1日のうち、一連のトラックで陸を通過するまで待機することができます。

_推奨される初期ポート範囲_

|メディア トラフィックの種類| クライアントのソース ポートの範囲 |プロトコル|DSCP 値|DSCP クラス|
|:--- |:--- |:--- |:--- |:--- |
|オーディオ| 50,000–50,019|TCP/UDP|46|完全優先転送 (EF)|
|ビデオ| 50,020–50,039|TCP/UDP|34|相対的優先転送 (AF41)|
|アプリケーション/画面共有| 50,040–50,059|TCP/UDP|才|相対的優先転送 (AF21)|
||||||

これらの設定を使用する場合は、次の点に注意してください。

- 今後、ExpressRoute の実装を計画していて、QoS を実装していない場合は、このガイダンスに従うことをお勧めします。これにより、DSCP 値が送信者と受信者と同じになるようにすることをお勧めします。
- モバイルクライアントやチームデバイスを含むすべてのクライアントは、これらのポート範囲を使用します。また、これらのソースポート範囲を使用する、実装するすべての DSCP ポリシーが影響を受けます。 動的なポートを引き続き使用するクライアントは、ブラウザーベースのクライアント (つまり、参加者がブラウザーを使って会議に参加できるクライアント) だけです。
- Mac クライアントでは、同じポート範囲を使用しますが、オーディオ (EF) とビデオ (AF41) にはハードコーディングされた値も使用されます。 これらの値は構成できません。
- ユーザーエクスペリエンスを向上させるために、後でポート範囲を調整する必要がある場合は、ポート範囲を重ねる必要があり、互いに隣り合っている必要があります。

## <a name="migrate-qos-to-teams"></a>QoS を Teams に移行する

以前に Skype for Business Online を展開したことがある場合 (QoS のタグ付けやポート範囲を含む)、展開されている場合。 Teams では、チームは既存の構成を尊重し、Skype for Business クライアントと同じポート範囲とタグ付けを使用します。 ほとんどの場合、追加の構成は必要ありません。

> [!NOTE]
> グループポリシーによってアプリケーション名の QoS タグ付けを使用している場合は、アプリケーション名として Teams.exe を追加する必要があります。

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>PowerShell を使用して Windows 上のチームに QoS を実装する

**オーディオ用に QoS を設定する**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**ビデオに QoS を設定する**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**共有用に QoS を設定する**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Teams 管理センターでソースポートを管理する

Teams では、さまざまなワークロードによって使用される QoS ソースポートを、必要に応じて動的に管理し、調整する必要があります。 「 [各メディアの種類の初期ポート範囲を選択](#choose-initial-port-ranges-for-each-media-type)する」の表を参照すると、ポート範囲は調整できますが、DSCP マーキングは構成できません。 これらの設定を実装した後は、特定のメディアの種類に必要なポートの数が増加したり、少ない場合があります。 [ユーザーごとの通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md) と [通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md) を使用して、Teams が実装された後、定期的に、必要に応じて、ポート範囲を調整することをお勧めします。

> [!NOTE]
> Skype for Business Online のソースポート範囲と DSCP マーキングに基づいて既に QoS を構成している場合は、同じ構成が Teams に適用され、マッピングに対するクライアントやネットワークの変更は必要ありませんが、 [チームで使用する範囲を設定](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) して、Skype For business online 用に構成されたものと一致させる必要があります。

以前にオンプレミスの Skype for Business Server を展開したことがある場合は、QoS ポリシーを再調査しなければならない場合があります。 検証したポート範囲の設定に合わせてポリシーを調整して、チームの品質ユーザーエクスペリエンスを提供します。

## <a name="validate-your-qos-implementation"></a>QoS の実装を検証する

QoS を有効にするには、GPO によって設定された DSCP 値が、通話の両端に存在している必要があります。 チームクライアントによって生成されたトラフィックを分析することで、チームの作業負荷トラフィックがネットワーク内を移動したときに、DSCP 値が変更または削除されないことを確認できます。

可能であれば、ネットワークの出口ポイントでトラフィックをキャプチャします。 スイッチまたはルータでポートミラーリングを使用して、この問題を解決することができます。

## <a name="implement-qos-for-other-devices"></a>他のデバイスに QoS を実装する

Intune、Surface、iOS、Android、Mac の QoS の実装については、次のトピックを参照してください。

- [Surface Hub 2S の QoS](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [Surface Hub の QoS](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [IOS、Android、Mac の QoS](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>関連項目

- [ビデオ : ネットワーク計画](https://aka.ms/teams-networking)

- [Microsoft Teams 用に組織のネットワークを準備する](prepare-network.md)

- [チームクライアントでの QoS の実装](QoS-in-Teams-clients.md)
