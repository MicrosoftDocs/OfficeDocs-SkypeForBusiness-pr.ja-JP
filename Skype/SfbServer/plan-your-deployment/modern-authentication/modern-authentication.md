---
title: Skype for Business での先進認証の計画
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
description: 他の製品との統合を含む、Skype for Business Server の認証と承認の計画に関するトピック
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221581"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="40f62-103">Skype for Business での認証と承認についての説明</span><span class="sxs-lookup"><span data-stu-id="40f62-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="40f62-104">認証と承認は関連する概念ですが、ユーザーにとってはさまざまな作業を行います。</span><span class="sxs-lookup"><span data-stu-id="40f62-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="40f62-105">単純な用語で記述された authenciation (認証) は、パスワード、コード、指紋、証明書、true であるユーザーについてのクレームの組み合わせ、またはこれらを組み合わせて使用することによって、パスワード、コード、指紋、証明書、またはこれらを組み合わせて使用することができます。</span><span class="sxs-lookup"><span data-stu-id="40f62-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="40f62-106">認証は、本人であることを証明するためのプロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="40f62-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="40f62-107">承認 (AuthZ) は、お客者の身元を確認した後にアクセス権を取得することに関係します。</span><span class="sxs-lookup"><span data-stu-id="40f62-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="40f62-108">表示、編集、またはその他のアクセスが許可されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="40f62-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="40f62-109">たとえば、SharePoint Online に対するサイトコレクション管理者のアクセス権は強力ですが、Skype for Business Online などの他のオンラインワークロードに切り替えた場合、ユーザーの問題をトラブルシューティングする権限を持つことがあり、サーバーの構成を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="40f62-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="40f62-110">Exchange Online などの3番目のワークロードでは、平均的なユーザーのアクセス権しか持っていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40f62-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="40f62-111">AuthZ は、サービス/アクセス負荷、アプリケーション、ファイル、およびその他のデータに対して、どの程度のアクセスが必要かを確認します。</span><span class="sxs-lookup"><span data-stu-id="40f62-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="40f62-112">この例では、SharePoint や Exchange online のようなオンラインプロパティを使用していますが、認証と AuthZ のプロセスはオンプレミスでもハイブリッドドでも同じ方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="40f62-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="40f62-113">最終的には、AAD 接続や ADFS などのツールは、オンプレミスのアカウントとパスワードをクラウドの AD (Azure AD) に同期することによって、または intruding のフローでは、ユーザーが自分の資格情報の入力を求められることはありません。たとえば、クラウドのワークロードを切り替えるときにシングルサインオンのシナリオを作成する</span><span class="sxs-lookup"><span data-stu-id="40f62-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="40f62-114">しかし、自分では、認証または承認の一部ではなく、そのメカニズムの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="40f62-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="40f62-115">現在、多くのテクノロジでは、これらのプロセス (認証と AuthZ) を1つのメカニズムと考えています。また、認証プロセスへの参照もいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="40f62-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="40f62-116">ユーザーアクセスの最初のステップは認証であることを覚えておくことが重要です。これは、ユーザーが本人であることを確認し、そのユーザーがアクセス権を判断するユーザーの知識を利用することです (Open Authorization または OAuth を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="40f62-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="40f62-117">認証と承認の計画に関するトピック</span><span class="sxs-lookup"><span data-stu-id="40f62-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="40f62-118">Skype for Business での先進認証 (ADAL) の使用方法</span><span class="sxs-lookup"><span data-stu-id="40f62-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="40f62-119">先進認証でサポートされている Skype for Business のトポロジ</span><span class="sxs-lookup"><span data-stu-id="40f62-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="40f62-120">従来の認証方法をネットワークの内部および外部にオフにする計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="40f62-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

