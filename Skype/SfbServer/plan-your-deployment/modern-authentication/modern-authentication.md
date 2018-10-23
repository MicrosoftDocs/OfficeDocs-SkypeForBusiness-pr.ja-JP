---
title: Skype for Business での先進認証についての計画
ms.author: tracyp
author: MSFTTracyP
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 認証と承認 Skype の他の製品との統合を含め、ビジネス サーバーの計画に関するトピック
ms.openlocfilehash: 218100a78b128b28188d7c0b49534a9eb8ff4a1d
ms.sourcegitcommit: 6251a2c659909c3972ca2ea0a2bcdab4f334df34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2018
ms.locfileid: "25692719"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="10ed3-103">認証と承認 Skype のビジネスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="10ed3-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="10ed3-104">認証と承認、関連する概念が (ただし、両方は、必要に応じて)、自動的に別の作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="10ed3-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="10ed3-105">単純な用語で言えば、authenciation (認証) によって異なりますの機密情報だけで有効なユーザーを知っているが、およびパスワード、コード、指紋認証、証明書が true の場合、ユーザーに関するクレームの組み合わせまたは組み合わせこれらのものを一緒に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="10ed3-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="10ed3-106">各種の認証は、確かに本人であることを証明するアウト プロセスです。</span><span class="sxs-lookup"><span data-stu-id="10ed3-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="10ed3-107">承認 (AuthZ) は、どのようなアクセスを持つユーザーを実証した後です。</span><span class="sxs-lookup"><span data-stu-id="10ed3-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="10ed3-108">どのような許可するようされて表示、編集、およびそれ以外の場合にアクセスすることを決定します。</span><span class="sxs-lookup"><span data-stu-id="10ed3-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="10ed3-109">などを SharePoint Online では、強力なサイト コレクションの管理者のアクセスする必要がありますが、ユーザーの問題のトラブルシューティングを行うの構成を変更する特権がある場合がありますのビジネス オンラインでは、Skype のように、別のオンライン ワークロードに切り替えた場合、サーバーまたはサーバー。</span><span class="sxs-lookup"><span data-stu-id="10ed3-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="10ed3-110">Exchange Online など、3 つ目のワークロードでは、平均的なユーザーのアクセスのみがあります。</span><span class="sxs-lookup"><span data-stu-id="10ed3-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="10ed3-111">AuthZ は、サービス/ワークロードで、アプリケーション、ファイル、およびその他のデータする必要があるどのようなどのくらいのアクセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="10ed3-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="10ed3-112">例は、オンラインのプロパティ SharePoint とオンラインでの Exchange ですが、各種の認証および AuthZ のプロセスの作業、設置型と同様に、ハイブリッドの設置型では。</span><span class="sxs-lookup"><span data-stu-id="10ed3-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="10ed3-113">AAD を接続し、ad FS になるに関連する各種の認証および AuthZ ストーリーか、同期中、オンプレミス アカウントとパスワードをクラウドになどを最終的には、ツールの (である場合は、Office 365 または Azure Azure AD) AD の場合、または、AuthZ の流れに侵入します。頻繁に入力が不要、資格情報とシングル サインオンのシナリオを作成する、クラウドで作業負荷を切り替えるときです。</span><span class="sxs-lookup"><span data-stu-id="10ed3-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD in the case of either Office 365 or Azure), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="10ed3-114">自身であるため、担当する各種の認証または AuthZ、整備士の一部のみはないです。</span><span class="sxs-lookup"><span data-stu-id="10ed3-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="10ed3-115">本日は、多くのテクノロジは、(認証および AuthZ) の 1 つのメカニズムでは、これらのプロセスを検討してください、認証プロセスにもそれらの承認を含む多くの事例を聞きます。</span><span class="sxs-lookup"><span data-stu-id="10ed3-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="10ed3-116">ユーザー アクセスの最初のステップであることを証明する本人は、各種の認証および AuthZ を使用することを確認するのにどのような彼または彼女へのアクセス (未処理の認証と OAuth が表示されます)、ユーザーは、ユーザーの知識を覚えておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="10ed3-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="10ed3-117">認証および承認の計画のトピック</span><span class="sxs-lookup"><span data-stu-id="10ed3-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="10ed3-118">How to use Modern Authentication (ADAL) with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="10ed3-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="10ed3-119">Skype for Business topologies supported with Modern Authentication</span><span class="sxs-lookup"><span data-stu-id="10ed3-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="10ed3-120">無効にする従来の認証方法内部と外部のネットワークを計画しています。</span><span class="sxs-lookup"><span data-stu-id="10ed3-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

