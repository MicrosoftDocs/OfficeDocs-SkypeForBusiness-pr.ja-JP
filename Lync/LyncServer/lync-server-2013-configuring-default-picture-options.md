---
title: 'Lync Server 2013: 既定のピクチャオプションの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24d32ca52df9c75cf2a0816ff81bd5eaa775d22a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="ca929-102">Lync Server 2013 での既定の画像のオプションの構成</span><span class="sxs-lookup"><span data-stu-id="ca929-102">Configuring default picture options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca929-103">_**トピックの最終更新日:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="ca929-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="ca929-104">既定では、ユーザーの画像が自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca929-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="ca929-105">ユーザーが画像を非表示にする場合は、Lync クライアントで [**自分の画像を表示**しない] オプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ca929-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="ca929-106">ただし、この設定は他の Office アプリケーションでは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ca929-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="ca929-107">ユーザーによって無効にされていても画像が表示される可能性がある場合は、Lync 画像の表示設定をグローバルに、またはサイトまたはサービス用に変更して、ユーザーの画像が既定で表示されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ca929-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="ca929-108">次の Lync Server 管理シェルコマンドレットを使用して、クライアントで [**自分の画像を表示**する] オプションを明示的に選択しない限り、ユーザーの画像が表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="ca929-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="ca929-109">このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csprivacyconfiguration 戻し](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca929-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

