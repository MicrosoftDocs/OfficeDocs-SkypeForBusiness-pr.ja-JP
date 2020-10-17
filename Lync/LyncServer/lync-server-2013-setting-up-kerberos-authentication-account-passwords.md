---
title: 'Lync Server 2013: Kerberos 認証アカウントのパスワードの設定'
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
ms.openlocfilehash: 29e8887f35e6d60d7d3aa59a0aa05590df371618
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509674"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="eac58-102">Lync Server 2013 での Kerberos 認証アカウントパスワードの設定</span><span class="sxs-lookup"><span data-stu-id="eac58-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eac58-103">_**トピックの最終更新日:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="eac58-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="eac58-104">Kerberos 認証アカウントのコンピューター オブジェクトを作成したら、そのアカウント用のパスワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="eac58-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="eac58-105">Windows PowerShell コマンドレットを実行して、1台のサーバーで Kerberos アカウントのパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="eac58-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="eac58-106">Kerberos 認証のために作成したオブジェクトにパスワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="eac58-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="eac58-107">このパスワードは既知の値に設定することができますが、既定値はランダムなパスワードです。</span><span class="sxs-lookup"><span data-stu-id="eac58-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="eac58-108">このパスワードは、このアカウントを使用するすべての Kerberos 認証ソースを利用できます。</span><span class="sxs-lookup"><span data-stu-id="eac58-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="eac58-109">Kerberos アカウントのパスワードを設定して管理するには、Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eac58-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eac58-110">Kerberos アカウントオブジェクトはコンピューターオブジェクトですが、参照されている Windows PowerShell コマンドレットの操作には UserAccount パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="eac58-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="eac58-111">これは間違いではなく、このコマンドレットを Kerberos のアカウントの作成および管理に使用するときの、意図的な動作です。</span><span class="sxs-lookup"><span data-stu-id="eac58-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eac58-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eac58-112">In This Section</span></span>

  - [<span data-ttu-id="eac58-113">Lync Server 2013 のサーバーで Kerberos 認証アカウントのパスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="eac58-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="eac58-114">Lync Server 2013 で Kerberos 認証アカウントのパスワードを IIS に同期させる</span><span class="sxs-lookup"><span data-stu-id="eac58-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

