---
title: Skype for Business での先進認証についての計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 他の製品との統合など、Skype for Business Server の認証と承認の計画トピック
ms.openlocfilehash: f732e4afa6b82554c4248a244276e5e5b60c71cc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815845"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="977bf-103">Skype for Business での認証と承認について</span><span class="sxs-lookup"><span data-stu-id="977bf-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="977bf-104">認証と承認は関連する概念ですが、さまざまな作業を行います (ただし、どちらも必要です)。</span><span class="sxs-lookup"><span data-stu-id="977bf-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="977bf-105">単純な用語を使用する場合、authenciation (AuthN) は、有効なユーザーが知っているか、持っていることがわかっている、またはパスワード、コード、指紋、証明書、真であるユーザーに関するクレームの組み合わせ、またはそれらを組み合わせて使用した秘密によって異なります。</span><span class="sxs-lookup"><span data-stu-id="977bf-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="977bf-106">AuthN は、自分が言っていることを証明するためのプロセスです。</span><span class="sxs-lookup"><span data-stu-id="977bf-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="977bf-107">承認 (AuthZ) は、お客様の身元を証明した後にアクセス権を持っているかどうかに関係します。</span><span class="sxs-lookup"><span data-stu-id="977bf-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="977bf-108">表示、編集、その他のアクセスが許可されているものを特定します。</span><span class="sxs-lookup"><span data-stu-id="977bf-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="977bf-109">たとえば、SharePoint Online に対しては、サイトコレクション管理者による強力なアクセスが可能ですが、Skype for Business Online などのオンラインのワークロードに切り替えると、ユーザーの問題のトラブルシューティングを行うことができ、サーバーまたはサーバー。</span><span class="sxs-lookup"><span data-stu-id="977bf-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="977bf-110">Exchange Online などの3つ目のワークロードでは、平均ユーザーのアクセス権しか持たない場合があります。</span><span class="sxs-lookup"><span data-stu-id="977bf-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="977bf-111">AuthZ は、サービス/権限のロード、アプリケーション、ファイル、その他のデータに対してどの程度のアクセス権を付与するかを確認します。</span><span class="sxs-lookup"><span data-stu-id="977bf-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="977bf-112">この例には、SharePoint や Exchange online などのオンラインプロパティが含まれていますが、AuthN と AuthZ のプロセスはオンプレミスとハイブリッドの内部でも同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="977bf-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="977bf-113">最終的には、AAD Connect や ADFS などのツールは、オンプレミスのアカウントとパスワードをクラウドの広告 (Office 365 または Azure の場合は Azure AD) に同期することによって、AuthN と AuthZ のストーリーに関与します。ユーザーは、資格情報の入力を頻繁に求められることはありません。たとえば、クラウドのワークロードを切り替えて、シングルサインオンシナリオを作成する場合です。</span><span class="sxs-lookup"><span data-stu-id="977bf-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD in the case of either Office 365 or Azure), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="977bf-114">ただし、it 担当者は、it の一部ではなく AuthN または AuthZ を担当しています。</span><span class="sxs-lookup"><span data-stu-id="977bf-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="977bf-115">現在、多くのテクノロジでは、これらのプロセス (AuthN と AuthZ) が1つのメカニズムであると考えられ、認証プロセスへの参照には、承認も含まれています。</span><span class="sxs-lookup"><span data-stu-id="977bf-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="977bf-116">ユーザーアクセスの最初の手順は AuthN であり、自分の身元を証明していることを証明します。また、その AuthZ は、ユーザーがアクセス権を持つユーザー (Open Authorization または OAuth を使用して表示されます) についての情報を使用していることを覚えておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="977bf-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="977bf-117">認証と承認の計画に関するトピック</span><span class="sxs-lookup"><span data-stu-id="977bf-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="977bf-118">How to use Modern Authentication (ADAL) with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="977bf-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="977bf-119">Skype for Business topologies supported with Modern Authentication</span><span class="sxs-lookup"><span data-stu-id="977bf-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="977bf-120">内部および外部のネットワークに対して従来の認証方法をオフにすることを計画しています。</span><span class="sxs-lookup"><span data-stu-id="977bf-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

