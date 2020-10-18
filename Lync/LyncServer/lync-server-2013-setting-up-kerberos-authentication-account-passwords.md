---
title: 'Lync Server 2013: Kerberos 認証アカウントのパスワードの設定'
description: 'Lync Server 2013: Kerberos 認証アカウントのパスワードの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614b1411f9454c39843f4e69cabbfc3b02986e51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577223"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="8c6e6-103">Lync Server 2013 での Kerberos 認証アカウントパスワードの設定</span><span class="sxs-lookup"><span data-stu-id="8c6e6-103">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c6e6-104">_**トピックの最終更新日:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="8c6e6-104">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="8c6e6-105">Kerberos 認証アカウントのコンピューター オブジェクトを作成したら、そのアカウント用のパスワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8c6e6-105">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="8c6e6-106">Windows PowerShell コマンドレットを実行して、1台のサーバーで Kerberos アカウントのパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="8c6e6-106">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="8c6e6-107">Kerberos 認証のために作成したオブジェクトにパスワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8c6e6-107">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="8c6e6-108">このパスワードは既知の値に設定することができますが、既定値はランダムなパスワードです。</span><span class="sxs-lookup"><span data-stu-id="8c6e6-108">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="8c6e6-109">このパスワードは、このアカウントを使用するすべての Kerberos 認証ソースを利用できます。</span><span class="sxs-lookup"><span data-stu-id="8c6e6-109">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="8c6e6-110">Kerberos アカウントのパスワードを設定して管理するには、Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c6e6-110">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c6e6-111">Kerberos アカウントオブジェクトはコンピューターオブジェクトですが、参照されている Windows PowerShell コマンドレットの操作には UserAccount パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c6e6-111">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="8c6e6-112">これは間違いではなく、このコマンドレットを Kerberos のアカウントの作成および管理に使用するときの、意図的な動作です。</span><span class="sxs-lookup"><span data-stu-id="8c6e6-112">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8c6e6-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8c6e6-113">In This Section</span></span>

  - [<span data-ttu-id="8c6e6-114">Lync Server 2013 のサーバーで Kerberos 認証アカウントのパスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="8c6e6-114">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="8c6e6-115">Lync Server 2013 で Kerberos 認証アカウントのパスワードを IIS に同期させる</span><span class="sxs-lookup"><span data-stu-id="8c6e6-115">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

