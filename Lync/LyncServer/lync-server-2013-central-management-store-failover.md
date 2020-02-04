---
title: Lync Server 2013 の中央管理ストアのフェールオーバー
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
ms.openlocfilehash: 38bde96b74fa1c00fc937a159c5e8e40df42d4dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a>Lync Server 2013 の中央管理ストアのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

全体管理ストアには、Lync 2013 展開のサーバーとサービスに関する構成データが含まれています。 これにより、Lync 2013 の展開を定義、セットアップ、管理、管理、説明、操作するために必要なデータの堅牢な schematized ストレージが提供されます。 また、データを検証して構成の一貫性を保ちます。

各 Lync 展開には1つの一元管理ストアが含まれています。これは、1つのフロントエンドプールのバックエンドサーバーによってホストされます。

一元管理ストアをホストしているプールを含むプールのペアリングを確立すると、バックアッププールにバックアップ全体管理ストアデータベースがセットアップされ、中央管理ストアサービスが両方のプールにインストールされます。 任意の時点で、2つの中央管理ストアデータベースの一方がアクティブなマスターになり、もう1つはスタンバイ状態になります。 コンテンツは、バックアップサービスによってアクティブなマスターからスタンバイにレプリケートされます。

中央管理ストアをホストしているプールに関連するプールのフェールオーバー中に、管理者は、フロントエンドプールをフェールオーバーする前に、中央管理ストアでフェールオーバーする必要があります。

障害が修復された後に中央管理ストアをフェールバックする必要はありません。 修復した後は、元のバックアッププールの中央管理ストアをアクティブなマスターとして残すことができます。

中央管理ストアのフェールオーバーのエンジニアリング目標は、5 分の目標復旧時間 (RTO) と 5 分の目標復旧ポイント (RPO) です。

</div>

<span> </span>

</div>

</div>

</div>

