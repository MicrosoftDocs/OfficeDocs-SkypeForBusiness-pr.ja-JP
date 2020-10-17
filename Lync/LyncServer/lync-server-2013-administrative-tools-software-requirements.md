---
title: 'Lync Server 2013: 管理ツールのソフトウェア要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7c7b08d22933947c2f8079a2713fd134feb4629
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509044"
---
# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Lync Server 2013 の管理ツールソフトウェア要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

このトピックでは、オペレーティングシステムの要件に加えて、Lync Server 2013 の管理ツールをインストールして使用するために必要なソフトウェアについて説明します。

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server 2013 では、64ビット版の Microsoft .NET Framework 4.5 が必要です。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Microsoft Lync Server 2013 のコンポーネントを実行するには、Windows PowerShell 3.0 が必要です。 詳細については、「 [Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer Version 4.5

Lync Server 2013 は、Windows インストーラーテクノロジを使用して、さまざまなサーバーの役割をインストール、アンインストール、および保守します。 Windows Installer Version 4.5 は、Windows Server オペレーティング システムの再頒布可能なコンポーネントとして入手可能です。 Windows インストーラー4.5 は、Windows Server 2012 R2、Windows Server 2012、および Windows Server 2008 R2 と共に出荷されます。これは、Lync 2013 Server を実行しているコンピューターに対してユーティリティをダウンロードする必要がないことを意味します。 (Lync Server 2013 は、Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 を実行しているコンピューターにのみインストールできます。)

ただし、管理者ワークステーションに Lync Server 管理シェルまたは Lync Server トポロジビルダーをインストールする場合は、Windows インストーラー4.5 をダウンロードする必要がある場合があります。 このユーティリティには、windows 7 および windows 2008 R2 が付属していますが、Windows オペレーティングシステムの以前のバージョンには同梱されていません。 Windows インストーラー4.5 は、「Microsoft ダウンロードセンター」からダウンロードでき <https://go.microsoft.com/fwlink/p/?linkid=197395> ます。

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Microsoft Silverlight 5 ブラウザープラグイン

Lync Server 2013 コントロールパネルは web ベースのツールであり、Microsoft Silverlight 5 ブラウザープラグインの最新バージョンをインストールする必要があります。 Lync Server 2013 コントロールパネルを起動したときに、このソフトウェアがインストールされていない場合、または以前のバージョンがインストールされている場合は、Lync Server 2013 コントロールパネルで必要なバージョンをインストールするように求められます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)  


[Lync Server 2013 の管理ツールのインフラストラクチャ要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

