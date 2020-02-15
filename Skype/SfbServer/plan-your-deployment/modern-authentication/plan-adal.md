---
title: Skype for Business での先進認証 (ADAL) の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: この記事では、モダン認証 (Active Directory 認証ライブラリ (ADAL) および OAuth 2.0 に基づく) がどのようなものかについて説明します。
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046290"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="45d87-103">Skype for Business での先進認証 (ADAL) の使用方法</span><span class="sxs-lookup"><span data-stu-id="45d87-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="45d87-104">この記事では、(Active Directory 認証ライブラリ (ADAL) および OAuth 2.0 を基にした) モダン認証 (skype for business Server 2015 の Skype for business の累積的な更新プログラム2016、または初期から入手可能) について説明します。Skype for Business Server 2019 のリリース。</span><span class="sxs-lookup"><span data-stu-id="45d87-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="45d87-105">ADAL とは</span><span class="sxs-lookup"><span data-stu-id="45d87-105">What is ADAL?</span></span>

<span data-ttu-id="45d87-106">ADAL は、「Active Directory 認証ライブラリ」の頭字語であり、OAuth 2.0 とともに、先進認証の underpinning です。</span><span class="sxs-lookup"><span data-stu-id="45d87-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="45d87-107">このコードライブラリは、ディレクトリ内のセキュリティで保護されたリソースをセキュリティトークンを介してクライアントアプリケーション (Skype for Business など) で使用できるようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="45d87-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="45d87-108">ADAL は OAuth 2.0 と連携して、多要素認証 (MFA) やその他の形式の SAML 認証など、より多くの認証と承認のシナリオを可能にします。</span><span class="sxs-lookup"><span data-stu-id="45d87-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="45d87-109">クライアントとして機能するさまざまなアプリは、セキュリティで保護されたリソースへの取得を支援する先進認証を活用することができます。</span><span class="sxs-lookup"><span data-stu-id="45d87-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="45d87-110">Skype for Business Server では、ユーザーがリソースに対して適切なレベルの承認を得るために、このテクノロジがオンプレミスのクライアントとオンプレミスのサーバーの間で使用されます。</span><span class="sxs-lookup"><span data-stu-id="45d87-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="45d87-111">モダン認証の会話 (ADAL と OAuth 2.0 に基づく) には、いくつかの要素が共通しています。</span><span class="sxs-lookup"><span data-stu-id="45d87-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="45d87-112">クライアントがリソースに対して要求を発行しています。この場合、クライアントは Skype for Business です。</span><span class="sxs-lookup"><span data-stu-id="45d87-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="45d87-113">クライアントが特定のレベルのアクセスを必要とするリソースがあり、このリソースはディレクトリサービスによって保護されています。この場合、リソースは Skype for Business Server です。</span><span class="sxs-lookup"><span data-stu-id="45d87-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="45d87-114">その他に、OAuth 接続 (つまり、リソースへのアクセスをユーザーに*許可する専用*の接続) があります。</span><span class="sxs-lookup"><span data-stu-id="45d87-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="45d87-115">(OAuth は、よりわかりやすい名前 ' ' サーバー間 ' auth によっても知られており、多くの場合、S2S と略記されます。)</span><span class="sxs-lookup"><span data-stu-id="45d87-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="45d87-116">Skype for Business Server モダン認証 (ADAL) 会話では、Skype for Business Server は ADFS (Windows Server 2012 R2 の ADFS 3.0) を介して通信します。</span><span class="sxs-lookup"><span data-stu-id="45d87-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="45d87-117">認証は他の Id プロバイダー (IdP) を使用して行われることがありますが、Skype for Business server を ADFS と直接通信するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45d87-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="45d87-118">Skype for Business Server と連携するように ADFS を構成していない場合は、 [adfs のインストール](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)を完了してください。</span><span class="sxs-lookup"><span data-stu-id="45d87-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="45d87-119">ADAL は、Skype for business Server 2015 用の2016年3月の累積的な更新プログラムに含まれています。また、構成を正常に行うには、Skype for business の累積的な更新プログラムの2016年3月をインストールする**必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="45d87-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="45d87-120">Skype for Business Server 2019 の場合は、製品の初期リリースから入手できます。</span><span class="sxs-lookup"><span data-stu-id="45d87-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45d87-121">最初のリリースでは、オンプレミス環境での先進認証がサポートされるのは、混合 Skype トポロジが関係しない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="45d87-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="45d87-122">たとえば、環境が純粋に Skype for Business Server の場合などです。</span><span class="sxs-lookup"><span data-stu-id="45d87-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="45d87-123">このステートメントは変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45d87-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="45d87-124">ADAL で使用されるコマンドを含む、ps1 ファイルを含む PowerShell パッケージは、正常な構成のためにダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="45d87-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="45d87-125">Skype for business で先進認証を実装する方法については、「 [skype For business で先進認証 (ADAL) を使用する方法](../../manage/authentication/use-adal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d87-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
