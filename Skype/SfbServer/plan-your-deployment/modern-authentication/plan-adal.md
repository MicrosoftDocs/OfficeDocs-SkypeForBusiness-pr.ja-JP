---
title: Skype for Business での最新認証 (ADAL) の計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: この記事では、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づくモダン認証について説明します。
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816227"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="a0bce-103">Skype for Business でモダン認証 (ADAL) を使用する方法</span><span class="sxs-lookup"><span data-stu-id="a0bce-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="a0bce-104">この記事では、2016 年 3 月の Skype for Business for Skype for Business の累積的な更新プログラム (Skype for Business Server 2015) または Skype for Business Server 2019 の最初のリリースにある Active Directory 認証ライブラリ (ADAL) および OAuth 2.0 に基づく) の最新認証について紹介します。</span><span class="sxs-lookup"><span data-stu-id="a0bce-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="a0bce-105">ADAL とは</span><span class="sxs-lookup"><span data-stu-id="a0bce-105">What is ADAL?</span></span>

<span data-ttu-id="a0bce-106">ADAL は 'Active Directory 認証ライブラリ' の頭字語であり、OAuth 2.0 と共に、モダン認証の下支えになります。</span><span class="sxs-lookup"><span data-stu-id="a0bce-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="a0bce-107">このコード ライブラリは、ディレクトリ内のセキュリティで保護されたリソースを、セキュリティ トークンを介してクライアント アプリケーション (Skype for Business など) で使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a0bce-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="a0bce-108">ADAL は OAuth 2.0 と一緒に動作し、多要素認証 (MFA) や SAML 認証のフォームなど、より多くの認証および承認シナリオを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a0bce-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="a0bce-109">クライアントとして機能するさまざまなアプリは、セキュリティで保護されたリソースの取得にモダン認証を活用できます。</span><span class="sxs-lookup"><span data-stu-id="a0bce-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="a0bce-110">Skype for Business Server では、このテクノロジは、ユーザーにリソースへの適切なレベルの承認を与えるために、オンプレミスのクライアントとオンプレミス サーバーの間で使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0bce-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="a0bce-111">(ADAL と OAuth 2.0 に基づく) 最新の認証の会話には、いくつかの要素が共通しています。</span><span class="sxs-lookup"><span data-stu-id="a0bce-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="a0bce-112">リソースの要求を行うクライアントがいます。この場合、クライアントは Skype for Business です。</span><span class="sxs-lookup"><span data-stu-id="a0bce-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="a0bce-113">クライアントが特定のレベルのアクセスを必要とするリソースが存在し、このリソースはディレクトリ サービスによってセキュリティ保護されます。この場合、リソースは Skype for Business Server です。</span><span class="sxs-lookup"><span data-stu-id="a0bce-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="a0bce-114">つまり、OAuth 接続は、リソースへのアクセスをユーザーに許可する専用の接続です。</span><span class="sxs-lookup"><span data-stu-id="a0bce-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="a0bce-115">(OAuth は、よりわかりやすい名前である "サーバー間" の認証でも知られています。多くの場合、S2S と省略されます)。</span><span class="sxs-lookup"><span data-stu-id="a0bce-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="a0bce-116">Skype for Business Server のモダン認証 (ADAL) の会話では、Skype for Business Server は ADFS (ADFS 3.0 Windows Server 2012 R2) を通じて通信します。</span><span class="sxs-lookup"><span data-stu-id="a0bce-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="a0bce-117">認証は他の ID プロバイダー (IdP) を使用して行う場合がありますが、Skype for Business サーバーは ADFS と直接通信するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0bce-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="a0bce-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a0bce-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="a0bce-119">ADAL は、Skype for Business Server 2015 の 2016 年 3 月の累積的な更新プログラムに含まれています。また、Skype for **Business** の 2016 年 3 月の累積的な更新プログラムをインストールする必要があります。また、構成を成功するために必要です。</span><span class="sxs-lookup"><span data-stu-id="a0bce-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="a0bce-120">Skype for Business Server 2019 では、製品の最初のリリースから利用できます。</span><span class="sxs-lookup"><span data-stu-id="a0bce-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0bce-121">最初のリリースでは、Skype トポロジが混在している場合にのみ、オンプレミス環境でのモダン認証がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a0bce-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="a0bce-122">たとえば、環境が純粋に Skype for Business Server の場合です。</span><span class="sxs-lookup"><span data-stu-id="a0bce-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="a0bce-123">このステートメントは変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0bce-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="a0bce-124">ADAL で使用されるコマンドを含む .ps1 ファイルを含む PowerShell パッケージは、構成を成功するためにダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0bce-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="a0bce-125">Skype for Business でモダン認証を実装する方法については、「Skype for Business でモダン認証[(ADAL)](../../manage/authentication/use-adal.md)を使用する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0bce-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
