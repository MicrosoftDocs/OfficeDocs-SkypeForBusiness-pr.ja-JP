---
title: Skype for Business で先進認証 (ADAL) を計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: この記事では、モダン認証 (Active Directory Authentication Library (ADAL) と OAuth 2.0 に基づく) がどのようなものであるかについて説明します。
ms.openlocfilehash: c984e2468e1735a46c5246806afc57dd67327990
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297296"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="73e62-103">Skype for Business で先進認証 (ADAL) を使用する方法</span><span class="sxs-lookup"><span data-stu-id="73e62-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="73e62-104">この記事では、Skype for business Server 2015 の2016年3月の累積更新プログラムに含まれている、(Active Directory 認証ライブラリ (ADAL) および OAuth 2.0 に基づく) 先進認証について説明します。または、最初から行うこともできます。Skype for Business Server 2019 のリリース。</span><span class="sxs-lookup"><span data-stu-id="73e62-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="73e62-105">ADAL とは</span><span class="sxs-lookup"><span data-stu-id="73e62-105">What is ADAL?</span></span>

<span data-ttu-id="73e62-106">ADAL は、'Active Directory Authentication Library (Active Directory 認証ライブラリ)' の頭文字であり、OAuth 2.0 と共に、先進認証の基礎となるものです。</span><span class="sxs-lookup"><span data-stu-id="73e62-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="73e62-107">このコードライブラリは、ディレクトリ内のセキュリティで保護されたリソースを、セキュリティトークンを介してクライアントアプリケーション (Skype for Business など) で利用できるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="73e62-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="73e62-108">ADAL は OAuth 2.0 と連携して、多要素認証 (MFA) やさまざまな形式の SAML Auth など、多様な認証および承認シナリオを可能にします。</span><span class="sxs-lookup"><span data-stu-id="73e62-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="73e62-109">先進認証は、クライアントとして動作するさまざまなアプリがリソースのセキュリティ保護の手段として利用しています。</span><span class="sxs-lookup"><span data-stu-id="73e62-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="73e62-110">Skype for Business Server では、このテクノロジをオンプレミスのクライアントとオンプレミスのサーバーの間で使うことで、ユーザーがリソースに適切なレベルの承認を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="73e62-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="73e62-111">先進認証の通信 (ADAL と OAuth 2.0 をベースに使用) には次のような共通要素があります。</span><span class="sxs-lookup"><span data-stu-id="73e62-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="73e62-112">クライアントがリソースに対する要求を行っています。この場合、クライアントは Skype for Business です。</span><span class="sxs-lookup"><span data-stu-id="73e62-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="73e62-113">クライアントが特定のレベルのアクセスを必要とするリソースがあります。このリソースは、ディレクトリサービスによって保護されます。この場合、リソースは Skype for Business Server になります。</span><span class="sxs-lookup"><span data-stu-id="73e62-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="73e62-114">OAuth 接続 (つまり、ユーザーによるリソースへのアクセスを*許可*する専用の接続) があります。</span><span class="sxs-lookup"><span data-stu-id="73e62-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="73e62-115">(OAuth は、"サーバー間の" 認証のわかりやすい名前でも知られています。また、多くの場合、S2S と略記されます)。</span><span class="sxs-lookup"><span data-stu-id="73e62-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="73e62-116">Skype for Business Server 先進認証 (ADAL) の会話では、Skype for Business Server は ADFS (Windows Server 2012 R2 の ADFS 3.0) 経由で通信します。</span><span class="sxs-lookup"><span data-stu-id="73e62-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="73e62-117">認証は、別の ID プロバイダー (IdP) を使用して行うことも可能ですが、Skype for Business Server は、ADFS と直接通信するよう構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73e62-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="73e62-118">Skype for Business Server で動作するように ADFS を構成していない場合は、 [adfs のインストール](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)を完了してください。</span><span class="sxs-lookup"><span data-stu-id="73e62-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="73e62-119">ADAL は、Skype for Business Server 2015 の2016年3月の累積更新プログラムに含まれており、Skype for Business \*\*\*\* の2016年3月の累積更新プログラムをインストールして、正常に構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="73e62-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="73e62-120">Skype for Business Server 2019 の場合は、製品の最初のリリースから入手できます。</span><span class="sxs-lookup"><span data-stu-id="73e62-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="73e62-121">初期のリリースでは、オンプレミス環境での先進認証は、混成の Skype トポロジーが使用されていない場合のみのサポートとなります。</span><span class="sxs-lookup"><span data-stu-id="73e62-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="73e62-122">たとえば、環境が純粋な Skype for Business Server の場合などです。</span><span class="sxs-lookup"><span data-stu-id="73e62-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="73e62-123">この記述は、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73e62-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="73e62-124">正しい構成には、.ps1 ファイルと ADAL で使用するコマンドが収録された PowerShell パッケージをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73e62-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="73e62-125">Skype for Business で先進認証を実装する方法については、「 [skype For business で先進認証 (ADAL) を使用する方法](../../manage/authentication/use-adal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e62-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
