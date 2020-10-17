---
title: Lync Server 2013 中央管理ストアのフェールオーバー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675f5b8e2880303a99897da18f44047c73961e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508044"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a>Lync Server 2013 での中央管理ストアのフェールオーバー

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

中央管理ストアには、Lync 2013 展開内のサーバーとサービスに関する構成データが含まれています。 これにより、Lync 2013 展開の定義、設定、管理、管理、説明、および運用に必要なデータの堅牢で schematized ストレージが提供されます。 また、CMS はこのデータを検証して構成の一貫性も保証します。

各 Lync 展開には、1つのフロントエンドプールのバックエンドサーバーによってホストされる1つの中央管理ストアが含まれています。

中央管理ストアをホストするプールを含むプールのペアを確立すると、バックアッププールにバックアップ中央管理ストアデータベースがセットアップされ、中央管理ストアサービスが両方のプールにインストールされます。 いずれかの時点で、2つの中央管理ストアデータベースのうちの1つがアクティブマスターで、もう1つはスタンバイです。 コンテンツは、バックアップサービスによってアクティブマスターからスタンバイにレプリケートされます。

中央管理ストアをホストしているプールのフェールオーバー中に、管理者はフロントエンドプールをフェールオーバーする前に、中央管理ストアをフェールオーバーする必要があります。

障害が修復された後、中央管理ストアをフェールバックする必要はありません。 修復後は、元のバックアッププールの中央管理ストアをアクティブマスターとして残すことができます。

中央管理ストアのフェールオーバーのためのエンジニアリング目標は、目標復旧時間 (RTO) と5分の目標復旧ポイント (RPO) です。

</div>

<span> </span>

</div>

</div>

</div>

