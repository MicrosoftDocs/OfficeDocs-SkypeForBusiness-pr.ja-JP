---
title: 'Lync Server 2013: 通話管理受付の構成'
TOCTitle: 通話管理受付の構成
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48273661
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での通話管理受付の構成

 

_**トピックの最終更新日:** 2012-09-21_

通話受付管理 (CAC) は、リアルタイム セッションが確立可能かどうかを、使用可能な帯域幅に基づいて判別するソリューションです。このソリューションは、輻輳したネットワーク上のユーザーに対して音声/ビデオの品質低下を防止するのに役立ちます。CAC は、音声およびビデオについてのみリアルタイム トラフィックを制御し、データ トラフィックには影響しません。CAC は、既定の WAN パスに必要な帯域幅がない場合に、インターネット パスを経由して通話をルーティングすることもあります。詳細については、「計画」のドキュメントの「[Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)」を参照してください。

ここでは、ネットワークに CAC を展開して管理する方法を例示する一連の手順例を示します。


> [!IMPORTANT]
> CAC を展開する前に、「計画」のドキュメントの「<A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">例: Lync Server 2013 での通話受付管理の組織要件の収集</A>」の説明に従って、エンタープライズ ネットワーク トポロジについての必要な情報をすべて収集する必要があります。また、「展開」のドキュメントの「<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync Server 2013 でフロントエンド プールまたは Standard Edition サーバーを定義および構成する</A>」の説明に従って CAC コンポーネントがインストールおよびアクティブ化されていることも確認してください。



> [!NOTE]
> ここに示す CAC の展開例と管理例のすべては、 Lync Server 管理シェルを使用して実行しています。代わりの方法として、 Lync Server コントロール パネルの [<strong>ネットワーク構成</strong>] セクションを使用して CAC を管理することもできます。


## このセクション中

  - [CAC のネットワーク地域の構成](lync-server-2013-configure-network-regions-for-cac.md)

  - [帯域幅ポリシー プロファイルの作成](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Lync Server 2013 での CAC のネットワーク サイトの構成](lync-server-2013-configure-network-sites-for-cac.md)

  - [CAC のネットワーク サイトとのサブネットの関連付け](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [ネットワーク地域リンクの作成](lync-server-2013-create-network-region-links.md)

  - [ネットワーク地域間ルートの作成](lync-server-2013;-create-network-interregion-routes.md)

  - [Lync Server 2013 でのネットワーク サイト間ポリシーの作成](lync-server-2013-create-network-intersite-policies.md)

  - [通話受付管理の有効化](lync-server-2013-enable-call-admission-control.md)

  - [通話受付管理の展開のチェック リスト](lync-server-2013-call-admission-control-deployment-checklist.md)

