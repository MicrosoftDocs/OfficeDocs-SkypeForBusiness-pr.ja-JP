---
title: WMI 下位互換パッケージをインストールする
description: WMI 下位互換パッケージをインストールします。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9062e209981fd180b8772801960bd94d2256513a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568993"
---
# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="b56a1-103">WMI 下位互換パッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="b56a1-103">Install WMI Backward Compatibility package</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b56a1-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b56a1-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b56a1-105">WMI 下位互換パッケージをインストールせずにトポロジ ビルダー マージ ウィザードを実行しようとすると、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b56a1-105">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="b56a1-106">![WMI エラーメッセージ](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI エラーメッセージ")</span><span class="sxs-lookup"><span data-stu-id="b56a1-106">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="b56a1-107">WMI 下位互換パッケージをインストールせずに **Merge-CsLegacytopology** コマンドレットを実行しようとすると、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b56a1-107">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="b56a1-108">![Windows PowerShell WMI プロバイダーエラー](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI プロバイダーエラー")</span><span class="sxs-lookup"><span data-stu-id="b56a1-108">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="b56a1-109">WMI 下位互換パッケージをインストールするには</span><span class="sxs-lookup"><span data-stu-id="b56a1-109">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="b56a1-110">インストールメディアから、[ \\ セットアップ AMD64 セットアップOCSWMIBC.MSI] に移動し \\ \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="b56a1-110">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="b56a1-111">OCSWMIBC.MSI をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b56a1-111">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b56a1-p101">OCSWMIBC.msi は、トポロジ ビルダー マージ ウィザードが実行されているコンピューターにインストールする必要があります。ただし、トポロジ内のすべてのフロントエンド サーバーに OCSWMIBC.msi をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b56a1-p101">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b56a1-114">OCSWMIBC.msi は、Lync Server 2013 コアコンポーネントと Lync Server 2013 管理シェルがインストールされているドメイン内の任意のコンピューターにインストールでき、Office Communications Server 2007 R2 トポロジ (WMI プロバイダーから Active Directory ドメインサービス (AD DS) および SQL Server へのアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b56a1-114">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

