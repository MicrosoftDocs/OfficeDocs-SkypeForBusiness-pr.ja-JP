---
title: 'Lync Server 2013: 外部ユーザーアクセスの展開'
description: 'Lync Server 2013: 外部ユーザーアクセスの展開。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af41a169fe3a72e440e95cfa370a16117fb828a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573443"
---
# <a name="deploying-external-user-access-in-lync-server-2013"></a>Lync Server 2013 での外部ユーザーアクセスの展開

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-09-23_

Microsoft Lync Server 2013 のエッジコンポーネントを展開すると、認証済みおよび匿名のリモートユーザー、フェデレーションパートナー (XMPP パートナーを含む)、モバイルクライアント、パブリックインスタントメッセージング (IM) サービスのユーザーなど、Lync Server を使用して組織内の他のユーザーと通信するための、組織の内部ネットワークにログインしていない外部ユーザーが使用できます。 Lync Server 2013 の展開および構成プロセスは、Lync Server 2010 とは大きく異なるものではありません。 インストールおよび管理用のツールは、Lync Server 2010 の場合とほぼ同じです。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 &nbsp; エッジサーバーのインストールと構成は、多くの場合、社内のチームとの間に多大な量の計画と調整を必要とする複雑なプロセスになることがあります。これには、セキュリティ、ネットワーク、ファイアウォール、ドメインネームシステム (DNS)、ロードバランサー、公開キー基盤 (PKI) の考慮事項などがあります。 外部アクセスコンポーネントを展開する前に、用意されている計画プロセスとドキュメントを確認して使用することを強くお勧めします。 これにより、展開プロセスを進める際に望ましくない変更や問題の数と頻度を制限することができます。 外部ユーザーアクセスの計画の詳細については、「 <A href="lync-server-2013-planning-for-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスの計画</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での外部ユーザーアクセスの展開チェックリスト](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [Lync Server 2013 の外部ユーザーアクセスコンポーネントのシステム要件](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [Lync Server 2013 でのエッジおよびディレクターのトポロジの構築](lync-server-2013-building-an-edge-and-director-topology.md)

  - [Lync Server でのディレクターのセットアップ 2013](lync-server-2013-setting-up-the-director.md) (オプション)

  - [Lync Server 2013 でのエッジサーバーのセットアップ](lync-server-2013-setting-up-edge-servers.md)

  - [Lync Server 2013 用のリバースプロキシサーバーのセットアップ](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [Lync Server 2013 での外部ユーザーアクセスのサポートの構成](lync-server-2013-configuring-support-for-external-user-access.md)

  - [Lync Server 2013 での Lync-Skype 接続のプロビジョニングガイド](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [Lync Server 2013 でのモビリティの展開](lync-server-2013-deploying-mobility.md)

  - [Lync Server 2013 でのエッジ展開の確認](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

