---
title: 'フェーズ 10: 従来のサイトを使用停止にする'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3140e3529ec9e4c48ca41c26963f833f89d9f929
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a>フェーズ 10: 従来のサイトを使用停止にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-16_

次のトピックでは、使用停止プールのガイダンス、および Office Communications Server 2007 R2 の従来の展開におけるサーバーとプールの非アクティブ化と削除について説明します。 このセクションに記載されているすべての手順が必要なわけではありません。 個々のトピックの情報を読んで、どの使用停止の手順を使用するかを判断してください。

<div>


> [!WARNING]  
> ダイヤルイン会議の会議ディレクトリを Lync Server 2013 にインポートした場合は、プールの使用停止を開始する前に、会議ディレクトリの所有権を Lync Server 2013 に移行することが重要です。 会議ディレクトリの所有権を最初に切り替えずにプールを使用停止すると、移行したすべての会議のダイヤルイン機能が動作しなくなります。 使用していたプールのそれぞれの会議ディレクトリについて、所有権を切り替えるための手順を 1 回ずつ実行する必要があります。



</div>

<div>


> [!IMPORTANT]  
> 従来の環境を使用停止にする前に、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) アプリケーションの移行およびアップグレードの詳細については、「」を参照してください。<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [会議ディレクトリを移動する](move-conference-directories.md)

  - [DNS SRV レコードを更新する](update-dns-srv-records_1.md)

  - [サーバーとプールの使用停止](decommissioning-servers-and-pools.md)

  - [BackCompatSite の削除](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

