---
title: Skype for Business でのモダン認証 (ADAL) の計画
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
description: この記事では、モダン認証 (Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) について説明します。
ms.openlocfilehash: 1df07491881b90efc16c97e7cd5cec0953cfb346
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096613"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="0fe3c-103">Skype for Business でモダン認証 (ADAL) を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0fe3c-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="0fe3c-104">この記事では、Skype for Business Server 2015 の Skype for Business の 2016 年 3 月の累積的な更新プログラム、または Skype for Business Server 2019 の初期リリースから見つかったモダン認証 (Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) について紹介します。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="0fe3c-105">ADAL とは</span><span class="sxs-lookup"><span data-stu-id="0fe3c-105">What is ADAL?</span></span>

<span data-ttu-id="0fe3c-106">ADAL は 'Active Directory 認証ライブラリ' の頭字語であり、OAuth 2.0 と共に、モダン認証の下支えです。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="0fe3c-107">このコード ライブラリは、ディレクトリ内のセキュリティで保護されたリソースを、セキュリティ トークンを介してクライアント アプリケーション (Skype for Business など) で利用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="0fe3c-108">ADAL は OAuth 2.0 と機能し、多要素認証 (MFA) などのより多くの認証および承認シナリオや、より多くの形式の SAML Auth を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="0fe3c-109">クライアントとして機能するさまざまなアプリは、セキュリティで保護されたリソースの取得に役立つモダン認証を活用できます。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="0fe3c-110">Skype for Business Server では、このテクノロジは、ユーザーにリソースに対する適切なレベルの承認を与えるために、オンプレミス のクライアントとオンプレミス サーバーの間で使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="0fe3c-111">最新の認証の会話 (ADAL と OAuth 2.0 に基づく) には、共通する要素があります。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="0fe3c-112">リソースの要求を行うクライアントがあります。この場合、クライアントは Skype for Business です。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="0fe3c-113">クライアントが特定のレベルのアクセスを必要とするリソースが存在し、このリソースはディレクトリ サービスによってセキュリティ保護されます。この場合、リソースは Skype for Business Server です。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="0fe3c-114">つまり、ユーザーにリソースへのアクセスを許可する専用の接続である OAuth接続があります。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="0fe3c-115">(OAuth は、"Server-to-Server" 認証というわかりやすい名前でも知られています。多くの場合、S2S と省略されます)。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="0fe3c-116">Skype for Business Server Modern Authentication (ADAL) の会話では、Skype for Business Server は ADFS (ADFS 3.0 in Windows Server 2012 R2) を介して通信します。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="0fe3c-117">認証は、他の ID プロバイダー (IdP) を使用して行う場合がありますが、Skype for Business サーバーは、ADFS と直接通信するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="0fe3c-118">Skype for Business Server で動作するように ADFS を構成していない場合は [、ADFS のインストールを完了してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>
  
<span data-ttu-id="0fe3c-119">ADAL は、Skype for Business Server 2015 の 2016 年 3 月の累積的な更新プログラムに含まれており、Skype for **Business** の 2016 年 3 月の累積的な更新プログラムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="0fe3c-120">Skype for Business Server 2019 では、製品の最初のリリースから利用できます。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0fe3c-121">最初のリリースでは、Skype トポロジが混在している場合にのみ、オンプレミス環境でのモダン認証がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="0fe3c-122">たとえば、環境が純粋に Skype for Business Server の場合です。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="0fe3c-123">このステートメントは変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="0fe3c-124">ADAL で使用されるコマンドを含む .ps1 ファイルを含む PowerShell パッケージをダウンロードして、構成を成功する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fe3c-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="0fe3c-125">Skype for Business でモダン認証を実装する方法については、「Skype for Business でモダン認証 [(ADAL) を使用する方法」を参照してください。](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span><span class="sxs-lookup"><span data-stu-id="0fe3c-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span></span>