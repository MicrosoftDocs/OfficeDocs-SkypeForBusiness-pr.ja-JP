---
title: 'Lync Server 2013: ネットワーク領域、サイト、およびサブネットの構成'
TOCTitle: ネットワーク領域、サイト、およびサブネットの構成
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48272323
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成

 

_**トピックの最終更新日:** 2013-02-24_

このセクションで説明する高度なエンタープライズ VoIP の各機能は、ネットワーク地域、ネットワーク サイト、およびサブネットの特定の構成要件を共有します。 たとえば、3 つの高度な機能のいずれでも、トポロジの各サブネットが特定の *ネットワーク サイト* に関連付けられていて、各ネットワーク サイトは *ネットワーク地域* に関連付けられている必要があります。


> [!IMPORTANT]
> 通話受付管理、E9-1-1、またはメディア バイパスのネットワーク構成を開始する前に、「計画」のドキュメントの「<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 の高度なエンタープライズ VoIP 機能のネットワーク設定</A>」のトピックにあるネットワーク設定の追加情報を必ず確認してください。ネットワーク構成 (主に通話受付管理について) の詳細については、「計画」のドキュメントの「<A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理サービス要件の定義</A>」も参照してください。



通話受付管理および E9-1-1 には、ネットワーク サイトの追加構成要件があります。

  - 通話受付管理では、WAN の帯域幅が制限されているサイトごとに *帯域幅ポリシー プロファイル* を指定する必要があります。 通話受付管理を展開する場合、ネットワーク サイトを構成する前に [帯域幅ポリシー プロファイルの作成](lync-server-2013-create-bandwidth-policy-profiles.md)を行う必要があります。

  - E9-1-1 では、サイトごとに *場所のポリシー* を指定する必要があります。 E9-1-1 を展開する場合、ネットワーク サイトを構成する前に [場所ポリシーの作成](lync-server-2013-create-location-policies.md)を行う必要があります。

## ネットワーク地域、ネットワーク サイト、サブネットの作成または変更

次のトピックには、ネットワーク地域およびネットワーク サイトを作成または変更するステップや、サブネットをネットワーク サイトに関連付けるステップが記載されています。 これらは、特定の高度なエンタープライズ VoIP 機能に固有のトピックではありません。

  - [Lync Server 2013 でのネットワーク領域の作成または変更](lync-server-2013-create-or-modify-a-network-region.md)

  - [Lync Server 2013 でのネットワーク サイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)

  - [Lync Server 2013 でのネットワーク サイトとサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)

