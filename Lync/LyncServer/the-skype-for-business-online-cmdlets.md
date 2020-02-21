---
title: Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online cmdlets
ms:assetid: 71f38305-fd8b-4013-83e1-cb742e3174c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362817(v=OCS.15)
ms:contentKeyID: 56558831
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02365bfeeed60a22ea467091ebb0f2c92b0fa3c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-cmdlets"></a><span data-ttu-id="607d9-102">Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="607d9-102">The Skype for Business Online cmdlets</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="607d9-103">_**トピックの最終更新日:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="607d9-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="607d9-104">Windows PowerShell を使用して Skype for business Online に接続すると、Skype for Business Online コマンドレットのコレクションがメモリ内のコンピューターにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="607d9-104">When you connect to Skype for Business Online by using Windows PowerShell, a collection of Skype for Business Online cmdlets is copied, in memory, to your computer.</span></span> <span data-ttu-id="607d9-105">これらのコマンドレットは、ローカルコンピューターに既にあるその他のコマンドレット (Windows PowerShell のインストール時にインストールされたコアコマンドレットを含む) に加えて、Skype for Business Online の展開と Skype for business Online の展開を管理するために利用できます。Business Online のユーザーアカウント。</span><span class="sxs-lookup"><span data-stu-id="607d9-105">These cmdlets, in addition to any other cmdlets you already have on your local computer (including the core cmdlets that are installed when you install Windows PowerShell), are then available for managing your Skype for Business Online deployment and your Skype for Business Online user accounts.</span></span> <span data-ttu-id="607d9-106">Skype for Business Online のコマンドレットについては、以下のトピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="607d9-106">The Skype for Business Online cmdlets are introduced in the following topics:</span></span>

  - [<span data-ttu-id="607d9-107">Skype for Business Online テナントの管理</span><span class="sxs-lookup"><span data-stu-id="607d9-107">Managing Skype for Business Online tenants</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-skype-for-business-online-organizations)

  - [<span data-ttu-id="607d9-108">Skype for Business Online でユーザーとユーザーアカウントのプロパティを管理する</span><span class="sxs-lookup"><span data-stu-id="607d9-108">Managing users and user account properties in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/user-accounts/user-accounts)

  - [<span data-ttu-id="607d9-109">Skype for Business Online のポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="607d9-109">Managing policies in Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-policies-with-office-365-powershell)

  - [<span data-ttu-id="607d9-110">Skype for business クライアントを Skype for business Online から管理する</span><span class="sxs-lookup"><span data-stu-id="607d9-110">Managing the Skype for Business client from Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365)

  - [<span data-ttu-id="607d9-111">Skype for Business Online での Exchange ユニファイドメッセージングとホスト型ボイスメールの管理</span><span class="sxs-lookup"><span data-stu-id="607d9-111">Managing Exchange Unified Messaging and hosted voice mail in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-exchange-unified-messaging-and-hosted-voicemail)

  - [<span data-ttu-id="607d9-112">外部ユーザーおよび組織との Skype for Business Online での通信の管理</span><span class="sxs-lookup"><span data-stu-id="607d9-112">Managing communications in Skype for Business Online with outside users and organizations</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users)

  - [<span data-ttu-id="607d9-113">Skype for Business Online の会議と会議の管理</span><span class="sxs-lookup"><span data-stu-id="607d9-113">Managing Skype for Business Online meetings and conferences</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/conferencing/conferencing-policies)

  - [<span data-ttu-id="607d9-114">Skype for Business Online での携帯電話とモバイルデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="607d9-114">Managing cell phones and mobile devices in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/set-up-mobile-policies-for-your-organization)

<div>

## <a name="see-also"></a><span data-ttu-id="607d9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="607d9-115">See Also</span></span>


[<span data-ttu-id="607d9-116">クイックリファレンス: Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="607d9-116">Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

