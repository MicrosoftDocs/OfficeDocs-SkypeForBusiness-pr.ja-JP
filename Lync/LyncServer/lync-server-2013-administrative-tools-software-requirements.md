---
title: 'Lync Server 2013: 管理ツールのソフトウェア要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95dfed4d6cf69950a0e17ab6826d79ee7e7a68cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Lync Server 2013 の管理ツールのソフトウェア要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

このトピックでは、オペレーティングシステムの要件に加えて、Lync Server 2013 管理ツールをインストールして使用するために必要なソフトウェアについて説明します。

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server 2013 では、64ビット版の Microsoft .NET Framework 4.5 が必要です。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Microsoft Lync Server 2013 のコンポーネントを実行するには、Windows PowerShell 3.0 が必要です。 詳細については、「 [Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows インストーラーバージョン4.5

Lync Server 2013 は、Windows インストーラーテクノロジを使用して、さまざまなサーバーの役割をインストール、アンインストール、維持します。 Windows インストーラーバージョン4.5 は、Windows Server オペレーティングシステムの再頒布可能コンポーネントとして提供されています。 Windows Installer 4.5 は windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 と共に出荷されているため、Lync Server 2013 を実行しているコンピューターでは、このユーティリティをダウンロードする必要はありません。 (Lync Server 2013 は、Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 を実行しているコンピューターにのみインストールできます)。

ただし、Lync Server 管理シェルまたは Lync Server Topology Builder を管理者のワークステーションにインストールする場合は、Windows インストーラー4.5 のダウンロードが必要になることがあります。 このユーティリティには windows 7 と Windows 2008 R2 が付属していますが、以前のバージョンの Windows オペレーティングシステムには付属していません。 Windows インストーラー4.5 は、Microsoft ダウンロードセンターからダウンロードでき<http://go.microsoft.com/fwlink/p/?linkid=197395>ます。

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Microsoft Silverlight 5 browser プラグイン

Lync Server 2013 コントロールパネルは web ベースのツールであり、Microsoft Silverlight 5 browser プラグインの最新バージョンをインストールする必要があります。 Lync Server 2013 コントロールパネルを起動したときに、このソフトウェアがインストールされていない場合、または以前のバージョンがインストールされている場合は、Lync Server 2013 コントロールパネルで、必要なバージョンをインストールするように求められます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)  


[Lync Server 2013 での管理ツールインフラストラクチャの要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

