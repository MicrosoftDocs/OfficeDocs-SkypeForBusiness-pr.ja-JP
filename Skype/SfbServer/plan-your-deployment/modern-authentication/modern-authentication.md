---
title: Plan for Modern Authentication in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 他の製品との統合を含む、Skype for Business Server の認証と承認の計画に関するトピック
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816247"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="2dbbf-103">Skype for Business での認証と承認について</span><span class="sxs-lookup"><span data-stu-id="2dbbf-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="2dbbf-104">認証と承認は関連する概念ですが、作業は異なります (両方とも必要です)。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="2dbbf-105">簡単に言うなら、認証 (AuthN) は、有効なユーザーだけが知っている、または持っているシークレットに依存します。パスワード、コード、指紋、証明書、ユーザーに関するクレームの組み合わせ、またはこれらが組み合わせて使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="2dbbf-106">AuthN は、自分が自分の言い分であることを証明するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="2dbbf-107">承認 (AuthZ) は、自分が誰かを証明した後にアクセスできる情報に関係します。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="2dbbf-108">表示、編集、その他のアクセスが許可されている内容が決定されます。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="2dbbf-109">たとえば、SharePoint Online への強力なサイト コレクション管理者アクセス権を持っている場合でも、Skype for Business Online など別のオンライン ワークロードに切り替える場合は、サーバーの構成を変更するのではなく、ユーザーの問題をトラブルシューティングする権限を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="2dbbf-110">Exchange Online などの 3 番目のワークロードでは、平均的なユーザーのアクセス権しか持てない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="2dbbf-111">AuthZ は、サービス/worloads、アプリケーション、ファイル、その他のデータに対して持っているアクセスの量と量を確認します。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="2dbbf-112">この例では、SharePoint や Exchange Online などのオンライン プロパティが含まれますが、AuthN と AuthZ のプロセスはオンプレミスとハイブリッドのオンプレミスで同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="2dbbf-113">最終的には、AAD Connect や ADFS などのツールは、オンプレミスのアカウントとパスワードをクラウドの AD (Azure AD) に同期するか、AuthZ のフローに侵入してユーザーに資格情報の入力を頻繁に求めなかったりすることで、AuthN や AuthZ のストーリーに関与します。たとえば、クラウド内のワークロードを切り替える際に、単一の Sign-On シナリオを作成します。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="2dbbf-114">ただし、このメカニズムの一部として、それ自体が責任を持つ AuthN や AuthZ というのではない。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="2dbbf-115">現在、多くのテクノロジでは、これらのプロセス (AuthN と AuthZ) が 1 つのメカニズムと見なされ、認証プロセスへの多くの参照が聞こえます。認証プロセスには承認も含まれます。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="2dbbf-116">ユーザー アクセスの最初のステップは AuthN であり、ユーザーが誰かの知識を使用してユーザーがアクセス権を持っているユーザーを判断します (Open Authorization または OAuth で確認できます)。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="2dbbf-117">認証と承認の計画に関するトピック</span><span class="sxs-lookup"><span data-stu-id="2dbbf-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="2dbbf-118">Skype for Business でモダン認証 (ADAL) を使用する方法</span><span class="sxs-lookup"><span data-stu-id="2dbbf-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="2dbbf-119">先進認証でサポートされている Skype for Business トポロジ</span><span class="sxs-lookup"><span data-stu-id="2dbbf-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="2dbbf-120">ネットワークの内部および外部で従来の認証方法をオフにする計画。</span><span class="sxs-lookup"><span data-stu-id="2dbbf-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

