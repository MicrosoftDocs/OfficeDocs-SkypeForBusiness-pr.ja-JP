---
title: 'Lync Server 2013: Outlook の有効化リストを更新する'
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
ms.openlocfilehash: f44de6e3b7756935829b008c585474e08f6f9969
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="67d40-102">Lync Server 2013 の Outlook 有効化リストを更新する</span><span class="sxs-lookup"><span data-stu-id="67d40-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67d40-103">_**最終更新日:** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="67d40-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="67d40-104">Microsoft Lync 2013 用のオンライン会議アドインは、Outlook のアドイン管理リストに含めるポリシーを作成することによって、ユーザーが常に有効にしていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="67d40-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="67d40-105">アドイン管理リストポリシーは、グループポリシー管理コンソールの Office 管理用テンプレートファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="67d40-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="67d40-106">[HKCU\\\\Software ポリシー\\] の下に、レジストリ\\キー\\が\\作成\\さ\\れます。 Microsoft Office 15.0 Outlook15 弾力性 AddinList。</span><span class="sxs-lookup"><span data-stu-id="67d40-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="67d40-107">このキーに ucaddin dll の値を追加して、常に有効にし、ユーザーが手動で無効にできないように ucaddin の値を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="67d40-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="67d40-108">Outlook アドインの一覧に ucaddin dll を追加するには</span><span class="sxs-lookup"><span data-stu-id="67d40-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="67d40-109">AddinList レジストリキーに、[HKCU\\Software\\ポリシー\\Microsoft\\Office\\15.0\\Outlook15\\弾力性\\AddinList] にある次の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="67d40-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="67d40-110">レジストリの種類 =\_REG SZ</span><span class="sxs-lookup"><span data-stu-id="67d40-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="67d40-111">Name = ucaddin .dll</span><span class="sxs-lookup"><span data-stu-id="67d40-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="67d40-112">値 = 1 (アドインを常に有効にし、エンドユーザーが管理できないことを指定します)</span><span class="sxs-lookup"><span data-stu-id="67d40-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

