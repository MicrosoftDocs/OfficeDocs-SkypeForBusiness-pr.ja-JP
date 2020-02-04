---
title: 'Lync Server 2013: 環境テストの問題'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65803ff396a9615787291de2d728fe63f3350d0b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Lync Server 2013 での環境テストの問題

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

ベストプラクティスアナライザーは、Lync Server 2013 環境がサポートされている構成であることを確認するための手段を提供します。 Active Directory ドメインサービスのチェックの一部として、ベストプラクティスアナライザーは次の操作を実行します。

  - Active Directory ドメインサービスのフォレストとスキーマの準備を確認します。

  - 展開内の Active Directory ドメインサービスのサイトとドメインの数を示します。

  - フォレストとドメインのレベルを確認します。

  - ドメインコントローラーのバージョンを確認します。

  - ドメイン、構成、およびスキーマの名前付けコンテキストを識別します。

  - 有効なユーザーの数を示します。

  - グローバル Active Directory ドメインサービスの設定が保存されている場所を確認します。

  - Lync Server のサービス接続ポイント (Scp) を確認します。

  - データベースのバージョンを示します。

<div>

## <a name="resolving-issues-with-the-environment"></a>環境の問題を解決する

環境テストで環境の問題が検出された場合、これらの問題は、Active Directory 構成の問題、または特定のサーバーで実行されているソフトウェアのレベルに起因している可能性があります。 たとえば、Windows Server 2000 を実行している環境内のドメインコントローラーを特定する場合は、警告が表示され、サポートされているバージョンの Windows Server にアップグレードする必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

