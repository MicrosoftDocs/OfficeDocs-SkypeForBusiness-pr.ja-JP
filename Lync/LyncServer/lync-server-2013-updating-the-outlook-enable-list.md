---
title: 'Lync Server 2013: Outlook enable list の更新'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1f71d1ef0ebcb6bc5f8aee8875c013a24a4de0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="af463-102">Lync Server 2013 の Outlook enable list の更新</span><span class="sxs-lookup"><span data-stu-id="af463-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af463-103">_**トピックの最終更新日:** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="af463-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="af463-104">Microsoft Lync 2013 用のオンラインミーティングアドインは、Outlook のアドイン管理リストに含まれるポリシーを作成することによって、常にユーザーが有効な状態を保つことができます。</span><span class="sxs-lookup"><span data-stu-id="af463-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="af463-105">アドイン管理リスト ポリシーは、グループ ポリシー管理コンソールの Office 管理テンプレート ファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="af463-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="af463-106">[HKCU\\\\Software Policies\\Microsoft\\Office\\15.0\\Outlook15\\弾力性\\AddinList] の下にレジストリキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="af463-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="af463-107">このキーに ucaddin の値を追加し、その値を常に有効にして、ユーザーが手動で無効にできないように ucaddin を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="af463-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="af463-108">Outlook アドインの一覧に ucaddin を追加するには</span><span class="sxs-lookup"><span data-stu-id="af463-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="af463-109">AddinList レジストリキーに、[HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\弾力性\\AddinList] の下にある次の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="af463-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="af463-110">レジストリの種類 =\_REG SZ</span><span class="sxs-lookup"><span data-stu-id="af463-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="af463-111">名前 = ucaddin.dll</span><span class="sxs-lookup"><span data-stu-id="af463-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="af463-112">値 = 1 (アドインが常に有効になりエンド ユーザーが管理できないことを指定します)</span><span class="sxs-lookup"><span data-stu-id="af463-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

