---
title: 現代での認証 (ADAL) Skype ビジネスの計画
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: この資料では、どのような近代的な認証、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) はについて説明します。
ms.openlocfilehash: 0c3aeef2480494e45a4d18589b3e3cdc6d9c5357
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213908"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="fd6c9-103">Skype for Business で先進認証 (ADAL) を使用する方法</span><span class="sxs-lookup"><span data-stu-id="fd6c9-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="fd6c9-104">この記事で紹介現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているビジネス サーバー 2015 年または最初から、Skype のビジネス用の Skype 用の累積的な更新ビジネス サーバー 2019 の Skype をリリースします。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="fd6c9-105">ADAL とは</span><span class="sxs-lookup"><span data-stu-id="fd6c9-105">What is ADAL?</span></span>

<span data-ttu-id="fd6c9-106">ADAL は、'Active Directory Authentication Library (Active Directory 認証ライブラリ)' の頭文字であり、OAuth 2.0 と共に、先進認証の基礎となるものです。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="fd6c9-107">このコード ライブラリは、(ビジネス用の Skype) のようなセキュリティ トークンを使用してクライアント ・ アプリケーションに利用可能なディレクトリにセキュリティで保護されたリソースを作成するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="fd6c9-108">ADAL は OAuth 2.0 と連携して、多要素認証 (MFA) やさまざまな形式の SAML Auth など、多様な認証および承認シナリオを可能にします。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="fd6c9-109">先進認証は、クライアントとして動作するさまざまなアプリがリソースのセキュリティ保護の手段として利用しています。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="fd6c9-110">ビジネス サーバーの Skype は、オンプレミスのクライアントとオンプレミスのサーバー間でユーザーにリソースへの承認の適切なレベルを提供するためにこの技術を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="fd6c9-111">先進認証の通信 (ADAL と OAuth 2.0 をベースに使用) には次のような共通要素があります。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="fd6c9-112">リソースの要求を行うクライアントが、この場合、クライアントは、ビジネスの Skype です。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="fd6c9-113">クライアントが特定のレベルのアクセスを必要とするリソースがある、ディレクトリ サービスがこのリソースがセキュリティで保護されたリソースのビジネス サーバー用の Skype はここで。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="fd6c9-114">OAuth の接続、つまり、他の接続がリソースにアクセスするユーザーを*承認*するのには専用です。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="fd6c9-115">(OAuth は 'サーバー' への認証に、わかりやすい名前で知られています、S2S と省略は、多くの場合)。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="fd6c9-116">ビジネス サーバー ・最新認証 (ADAL) 会話の Skype、Skype ビジネス サーバーの ADFS (Windows Server 2012 R2 の ad FS 3.0) を介して通信します。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="fd6c9-117">認証は、別の ID プロバイダー (IdP) を使用して行うことも可能ですが、Skype for Business Server は、ADFS と直接通信するよう構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="fd6c9-118">ビジネス サーバーの Skype 上で動作する ADFS を構成していない場合は、 [ad FS のインストール](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)を完了してください。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="fd6c9-119">ADAL は、2016年 3 月に含まれているビジネス サーバー 2015 年の Skype 用の累積的な更新および年 2016年 3 月のビジネスの**必要があります**Skype の累積的な更新プログラムをインストールし、正しい構成のために必要な。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="fd6c9-120">ビジネス サーバー 2019 の Skype は、製品の初期リリースから利用可能です。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd6c9-121">初期のリリースでは、オンプレミス環境での先進認証は、混成の Skype トポロジーが使用されていない場合のみのサポートとなります。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="fd6c9-122">環境がビジネス サーバーの Skype では純粋である場合などです。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="fd6c9-123">この記述は、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="fd6c9-124">正しい構成には、.ps1 ファイルと ADAL で使用するコマンドが収録された PowerShell パッケージをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd6c9-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="fd6c9-125">ビジネス用の Skype の最新の認証を実装する方法についてを参照してください:[ビジネス用の Skype で最新の認証 (ADAL) を使用する方法](../../manage/authentication/use-adal.md)</span><span class="sxs-lookup"><span data-stu-id="fd6c9-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
