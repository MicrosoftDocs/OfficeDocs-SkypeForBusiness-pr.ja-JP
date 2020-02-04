---
title: 'Lync Server 2013: アドレス帳管理のための Windows PowerShell コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ec10f3e3d3d58a790ddc60fd1af1d1b09765685
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="9149d-102">Lync Server 2013 のアドレス帳サービス用の Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="9149d-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9149d-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9149d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9149d-104">Lync Server には、アドレス帳サービスを管理して構成するための Windows PowerShell コマンドラインインターフェイスコマンドレットが数多く用意されています。</span><span class="sxs-lookup"><span data-stu-id="9149d-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="9149d-105">これらのコマンドレットの一部は、以前のバージョンの Office Communications Server で使用されていた ABServer .exe コマンドの代わりになります。</span><span class="sxs-lookup"><span data-stu-id="9149d-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="9149d-106">次のトピックでは、アドレス帳サービスに関する情報の設定、作成、取得に使用するコマンドレット、およびクライアントがアドレス帳サービスを取得するときにアドレス帳サービスで使用する Web サービスに関する情報を取得するために使用するコマンドレットについて説明します。ファイルと設定。</span><span class="sxs-lookup"><span data-stu-id="9149d-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="9149d-107">これらのすべてのコマンドレットは、管理ツールがインストールされているサーバーまたはワークステーションの Lync Server ツールの lync server 管理シェルを通じて発行されます。</span><span class="sxs-lookup"><span data-stu-id="9149d-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9149d-108">このセクション中</span><span class="sxs-lookup"><span data-stu-id="9149d-108">In This Section</span></span>

  - [<span data-ttu-id="9149d-109">Lync Server 2013 でのアドレス帳管理用の新しい CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="9149d-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="9149d-110">Lync Server 2013 でのアドレス帳管理用の設定-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="9149d-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="9149d-111">Lync Server 2013 でのアドレス帳管理のための設定を取得する</span><span class="sxs-lookup"><span data-stu-id="9149d-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="9149d-112">Lync Server 2013 でのアドレス帳管理用の削除-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="9149d-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="9149d-113">Lync Server 2013 でのアドレス帳管理用のテスト-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="9149d-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="9149d-114">Lync Server 2013 でのアドレス帳の管理に関するテスト-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="9149d-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="9149d-115">Lync Server 2013 でのアドレス帳管理の更新プログラム-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="9149d-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="9149d-116">Lync Server 2013 でのアドレス帳管理用の新しい CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="9149d-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="9149d-117">Lync Server 2013 でのアドレス帳管理のための CsClientPolicy の設定</span><span class="sxs-lookup"><span data-stu-id="9149d-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="9149d-118">Lync Server 2013 でのアドレス帳管理のための CsService</span><span class="sxs-lookup"><span data-stu-id="9149d-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="9149d-119">Lync Server 2013 でのアドレス帳管理のための CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="9149d-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="9149d-120">Lync Server 2013 でのアドレス帳管理の CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="9149d-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="9149d-121">Lync Server 2013 でのアドレス帳管理用に CsWebServiceConfiguration を設定する</span><span class="sxs-lookup"><span data-stu-id="9149d-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="9149d-122">Lync Server 2013 でのアドレス帳管理用の CsWebServiceConfiguration の削除</span><span class="sxs-lookup"><span data-stu-id="9149d-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="9149d-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="9149d-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9149d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9149d-124">See Also</span></span>


[http://go.microsoft.com/fwlink/p/?linkId=205826](http://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

