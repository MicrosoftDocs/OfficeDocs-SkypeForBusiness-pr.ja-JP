---
title: 'Lync Server 2013: 通話受付管理の計画'
TOCTitle: 通話受付管理 (CAC) の計画
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48273573
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での通話受付管理の計画

 

_**トピックの最終更新日:** 2012-09-21_

テレフォニー、ビデオ、およびアプリケーション共有などの IP ベースの統合コミュニケーション (UC) アプリケーションでは、通常、エンタープライズのネットワークで使用可能な帯域幅が LAN 環境内での制限因子とみなされることはありませんが、サイトを相互接続する WAN リンクではネットワーク帯域幅が制限される可能性があります。流入するネットワーク トラフィックによって 1 つの WAN リンクが過剰に予約されると、輻輳を解決するため、キュー、バッファー、およびパケット ドロップなどの最新のメカニズムが使用されます。一般に、余分なトラフィックはネットワークの輻輳が緩和されるまで遅延され、必要であれば、そのトラフィックはドロップされます。そのような状況にある従来のデータ トラフィックの場合、受信側のクライアントは回復できます。統合コミュニケーションなどのリアルタイム トラフィックの場合は、ネットワークの輻輳をこの方法で解決することはできません。これは、統合コミュニケーションのトラフィックが遅延とパケット損失両方の影響を受けやすいからです。WAN で輻輳が発生すると、ユーザーの QoE (Quality of Experience) が低下します。輻輳状態のリアルタイム トラフィックの場合は、低品質での接続を提供するよりも、通話を拒否する方が適切です。

通話受付管理 (CAC) では、リアルタイム セッションを許容品質で確立するのに十分なネットワーク帯域幅があるかどうかを判断します。 Lync Server 2013 において、CAC は音声ビデオについてのみリアルタイム トラフィックを制御し、データ トラフィックには影響しません。既定の WAN パスで必要な帯域幅が確保されていない場合、CAC はインターネット パスまたは公衆交換電話網 (PSTN) を利用した通話のルーティングを試みることができます。CAC は Lync Server でのみ使用できます。

ここでは、通話受付管理機能と CAC の計画方法を説明します。

> [!NOTE]
> Lync Server には、通話受付管理、緊急サービス (E9-1-1)、およびメディア バイパスという 3 つの高度な エンタープライズ VoIP 機能があります。これら 3 つの機能すべてに共通の計画情報の概要については、「<a href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 の高度なエンタープライズ VoIP 機能のネットワーク設定</a>」を参照してください。


## このセクション中

  - [Lync Server 2013 通話受付管理の概要](lync-server-2013-overview-of-call-admission-control.md)

  - [Lync Server 2013 での通話受付管理サービス要件の定義](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [例: Lync Server 2013 での通話受付管理の組織要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013 の CAC のコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013 の通話受付管理のベスト プラクティス](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013 の通話受付管理の展開チェックリスト](lync-server-2013-deployment-checklist-for-call-admission-control.md)

