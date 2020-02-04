---
title: 'Lync Server 2013: 2 要素認証の計画と展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and deploying two-factor authentication
ms:assetid: 442a88df-ebc2-4335-9c59-0ce1adc1471e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308563(v=OCS.15)
ms:contentKeyID: 54973686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a7aa10719a357100ce38da6616ef6c79d6a4a10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="b255e-102">Lync Server 2013 での2要素認証</span><span class="sxs-lookup"><span data-stu-id="b255e-102">Two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b255e-103">_**最終更新日:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="b255e-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="b255e-104">2要素認証は、ユーザー名とパスワードの組み合わせとトークンまたは証明書の2つの認証条件を満たすようにユーザーに要求することで、セキュリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="b255e-104">Two-factor authentication provides improved security by requiring users to meet two authentication criteria: a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="b255e-105">この方式は、"知っていることと持っているもの" とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b255e-105">This is also known as “something you have, something you know.”</span></span> <span data-ttu-id="b255e-106">証明書を使用した 2 要素認証の一般的な例として、スマート カードの使用があります。</span><span class="sxs-lookup"><span data-stu-id="b255e-106">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="b255e-107">スマート カードにはユーザー アカウントに関連付けられている証明書が格納されていて、サーバーに格納されているユーザー情報と証明書情報に対する検証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b255e-107">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="b255e-108">ユーザー情報 (ユーザー名とパスワード) と提供された証明書を比較することで、サーバーでは資格情報を検証し、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="b255e-108">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b255e-109">このセクション中</span><span class="sxs-lookup"><span data-stu-id="b255e-109">In This Section</span></span>

[<span data-ttu-id="b255e-110">Lync Server 2013 での2要素認証の計画</span><span class="sxs-lookup"><span data-stu-id="b255e-110">Planning for two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-planning-for-two-factor-authentication.md)

[<span data-ttu-id="b255e-111">Lync Server 2013 での2要素認証の構成</span><span class="sxs-lookup"><span data-stu-id="b255e-111">Configuring two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-configuring-two-factor-authentication.md)

[<span data-ttu-id="b255e-112">Lync クライアントおよび Lync Server 2013 での2要素認証の使用</span><span class="sxs-lookup"><span data-stu-id="b255e-112">Using two-factor authentication with Lync client and Lync Server 2013</span></span>](lync-server-2013-using-two-factor-authentication-with-lync-client.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

