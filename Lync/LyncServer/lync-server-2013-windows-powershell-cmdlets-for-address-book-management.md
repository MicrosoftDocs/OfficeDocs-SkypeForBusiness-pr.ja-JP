---
title: 'Lync Server 2013: アドレス帳管理用の Windows PowerShell コマンドレット'
description: 'Lync Server 2013: アドレス帳管理用の Windows PowerShell コマンドレット。'
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
ms.openlocfilehash: b598d91a4d1a29a67d8f8ceb2477f2d9b96f1319
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546023"
---
# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="74077-103">Lync Server 2013 のアドレス帳サービス用の Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="74077-103">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74077-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="74077-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="74077-105">Lync Server には、アドレス帳サービスを管理および構成するための Windows PowerShell コマンドラインインターフェイスコマンドレットが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="74077-105">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="74077-106">これらのコマンドレットの一部は、以前のバージョンの Office Communications Server で使用された ABServer.exe コマンドに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="74077-106">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="74077-107">以下のトピックには、アドレス帳サービスとその構成に関する情報や、クライアントでアドレス帳サービスのファイルや設定を取得する際にアドレス帳サービスが使用する Web サービスの情報について、設定、作成、および取得を行うために使用するコマンドレットが記載されています。</span><span class="sxs-lookup"><span data-stu-id="74077-107">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="74077-108">これらのすべてのコマンドレットは、管理ツールがインストールされているサーバーまたはワークステーションの Lync server ツールにある Lync Server 管理シェルを介して発行されます。</span><span class="sxs-lookup"><span data-stu-id="74077-108">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="74077-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="74077-109">In This Section</span></span>

  - [<span data-ttu-id="74077-110">Lync Server 2013 でのアドレス帳管理用の新しい-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="74077-110">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="74077-111">Lync Server 2013 でのアドレス帳管理用の設定-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="74077-111">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="74077-112">Lync Server 2013 でのアドレス帳管理用の-CsAddressBookConfiguration の取得</span><span class="sxs-lookup"><span data-stu-id="74077-112">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="74077-113">Lync Server 2013 でのアドレス帳管理用の-CsAddressBookConfiguration の削除</span><span class="sxs-lookup"><span data-stu-id="74077-113">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="74077-114">Lync Server 2013 でのアドレス帳管理用のテスト-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="74077-114">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="74077-115">Lync Server 2013 でのアドレス帳管理用のテスト-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="74077-115">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="74077-116">Update-csaddressbook Lync Server 2013 でのアドレス帳管理のための更新プログラム</span><span class="sxs-lookup"><span data-stu-id="74077-116">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="74077-117">Lync Server 2013 でのアドレス帳管理用の新しい-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="74077-117">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="74077-118">Lync Server 2013 でのアドレス帳管理用の設定-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="74077-118">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="74077-119">Lync Server 2013 でのアドレス帳管理のための CsService</span><span class="sxs-lookup"><span data-stu-id="74077-119">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="74077-120">Set-cswebserviceconfiguration Lync Server 2013 でのアドレス帳管理のための新しい手順</span><span class="sxs-lookup"><span data-stu-id="74077-120">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="74077-121">Set-cswebserviceconfiguration Lync Server 2013 でのアドレス帳管理のための取得</span><span class="sxs-lookup"><span data-stu-id="74077-121">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="74077-122">Set-cswebserviceconfiguration Lync Server 2013 でのアドレス帳管理用の設定</span><span class="sxs-lookup"><span data-stu-id="74077-122">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="74077-123">Set-cswebserviceconfiguration Lync Server 2013 でのアドレス帳管理のための削除</span><span class="sxs-lookup"><span data-stu-id="74077-123">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="74077-124">関連するセクション</span><span class="sxs-lookup"><span data-stu-id="74077-124">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74077-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="74077-125">See Also</span></span>


[https://go.microsoft.com/fwlink/p/?linkId=205826](https://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

