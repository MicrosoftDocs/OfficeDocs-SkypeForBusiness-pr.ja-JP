---
title: Microsoft Teams のルームでの認証
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Microsoft Teams ルームの先進認証の構成方法について説明します
ms.openlocfilehash: bef547ab0b9ade2edc433ec64bb1ef61eee4c040
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160114"
---
# <a name="authentication-in-microsoft-teams-rooms"></a><span data-ttu-id="afe7f-103">Microsoft Teams のルームでの認証</span><span class="sxs-lookup"><span data-stu-id="afe7f-103">Authentication in Microsoft Teams Rooms</span></span>

<span data-ttu-id="afe7f-104">Microsoft Teams 会議室デバイスのアカウント管理は、アプリケーションレベルで処理されます。</span><span class="sxs-lookup"><span data-stu-id="afe7f-104">Account management for Microsoft Teams Rooms devices is handled at the application level.</span></span> <span data-ttu-id="afe7f-105">アプリケーションは、Microsoft Teams、Skype for Business、Exchange に接続して、room アカウントのリソースを取得して、通話と会議のエクスペリエンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="afe7f-105">The application connects to Microsoft Teams, Skype for Business, and Exchange to get resources for the room account to enable calling and meeting experiences.</span></span> <span data-ttu-id="afe7f-106">このデバイスは、常に機能するための限定されたものであり、通話プランを使って構成されているデバイスの場合は、そのデバイスに実装されているカスタムロックダウンメカニズムを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="afe7f-106">The device is kept account agnostic to allow for always-on capabilities, calling scenarios (for devices configured with a Calling Plan), and custom lockdown mechanisms implemented on these devices.</span></span> <span data-ttu-id="afe7f-107">これは、これらのデバイスの認証は、エンドユーザーのデバイスとは異なる方法で行われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="afe7f-107">This means that authentication for these devices happen in a different way than for end-user devices.</span></span>  

<span data-ttu-id="afe7f-108">Microsoft Teams 室のデバイスを Office 365 で使用しているすべてのユーザーは、モダン認証をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="afe7f-108">Modern authentication is recommended for all customers using Microsoft Teams Rooms devices with Office 365.</span></span> <span data-ttu-id="afe7f-109">Exchange server または Skype for Business server のオンプレミス展開を使用している場合は、先進認証を有効にするために Azure Active Directory (Azure AD) との[ハイブリッド先進認証](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)を構成します。</span><span class="sxs-lookup"><span data-stu-id="afe7f-109">If you have an on-premises deployment of Exchange server or Skype for Business server, configure [hybrid modern authentication](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) with Azure Active Directory (Azure AD) to enable using modern authentication.</span></span>

<span data-ttu-id="afe7f-110">先進認証は、Microsoft Teams の会議室バージョン4.4.25.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="afe7f-110">Modern authentication is supported on Microsoft Teams Rooms version 4.4.25.0 and later.</span></span>

## <a name="modern-authentication"></a><span data-ttu-id="afe7f-111">先進認証</span><span class="sxs-lookup"><span data-stu-id="afe7f-111">Modern authentication</span></span>

<span data-ttu-id="afe7f-112">Microsoft Teams の会議室のアプリケーションで先進認証を使用する場合、Microsoft Teams、Exchange、Skype for Business への接続に Active Directory Authentication Library (ADAL) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="afe7f-112">When you use modern authentication with the Microsoft Teams Rooms application, Active Directory Authentication Library (ADAL) is used to connect to Microsoft Teams, Exchange, and Skype for Business.</span></span> <span data-ttu-id="afe7f-113">Microsoft Teams のルームデバイスは共有デバイスであり、夜間の再起動を実行して、スムーズに機能し、重要なオペレーティングシステム、ドライバー、ファームウェア、またはアプリケーションの更新プログラムを入手します。</span><span class="sxs-lookup"><span data-stu-id="afe7f-113">A Microsoft Teams Rooms device is a shared device and performs a nightly reboot to ensure smooth functioning and to get critical operating system, driver, firmware, or application updates.</span></span> <span data-ttu-id="afe7f-114">先進認証メカニズムでは、OAuth 2.0 での[リソース所有者のパスワード資格情報](https://tools.ietf.org/html/rfc6749#section-1.3.3)の許可の種類を使用します。これには、ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="afe7f-114">The modern authentication mechanism uses the [resource owner password credentials](https://tools.ietf.org/html/rfc6749#section-1.3.3) authorization grant type in OAuth 2.0, which doesn't require any user intervention.</span></span> <span data-ttu-id="afe7f-115">これは、Microsoft Teams のルームアプリケーションで使用されるユーザーアカウントとリソースアカウントの先進認証のしくみとの主な違いの1つです。</span><span class="sxs-lookup"><span data-stu-id="afe7f-115">This is one of the key differences between how modern authentication works for user accounts versus resource accounts that are used by the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="afe7f-116">このため、Microsoft Teams の会議リソースアカウントは、多要素認証 (MFA)、スマートカード認証、またはクライアント証明書ベースの認証を使用するように構成しないでください (すべてのエンドユーザーが使用可能)。</span><span class="sxs-lookup"><span data-stu-id="afe7f-116">Because of this, Microsoft Teams Rooms resource accounts shouldn't be configured to use multi-factor authentication (MFA), smart card authentication, or client certificate-based authentication (which are all available for end users).</span></span>

<span data-ttu-id="afe7f-117">Microsoft Teams の会議室のデバイスとエンドユーザーのデバイスでの先進認証の動作の主な違いは、リソースアカウントを使用して、"デバイスに対して苦情としてマークする"、"ハイブリッド Azure AD に参加しているデバイスを要求する" などのデバイスレベルの条件付きアクセスポリシーを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="afe7f-117">The other key difference between how modern authentication works on Microsoft Teams Rooms devices and end-user devices is that you can't use a resource account to apply device-level conditional access policies such as "Require device to be marked as complaint", or "Require Hybrid Azure AD joined device", and so on.</span></span> <span data-ttu-id="afe7f-118">これは、アプリケーションレベルで使用されている場合、デバイスレベルの概念が先進認証に適用されないためです。</span><span class="sxs-lookup"><span data-stu-id="afe7f-118">This is because device-level concepts don't apply to modern authentication when used at the application level.</span></span> <span data-ttu-id="afe7f-119">代わりに、[次](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess)のガイダンスを使用して、Microsoft Intune にデバイスを登録して、コンプライアンスポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="afe7f-119">Instead, you can enroll a device in Microsoft Intune and apply compliance policies by using the guidance [here](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).</span></span>

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a><span data-ttu-id="afe7f-120">Microsoft Teams 室のデバイスで先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="afe7f-120">Enable modern authentication on a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="afe7f-121">Microsoft Teams のルームで Skype for Business と Exchange の先進認証を使用するには、Microsoft Teams 室のデバイスでの先進認証のクライアント側設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="afe7f-121">For Microsoft Teams Rooms to use modern authentication with Skype for Business and Exchange, enable the client-side setting for modern authentication on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="afe7f-122">これは、デバイスの設定または XML 構成ファイルで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="afe7f-122">You can do this in the device settings or in the XML config file.</span></span>

> [!NOTE]
> <span data-ttu-id="afe7f-123">先進認証のためにクライアント側の設定を有効にする前に、先進認証を使用するように環境が正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-123">Before you enable the client-side setting for modern authentication, make sure that your environment is set up correctly to use modern authentication.</span></span>

### <a name="using-device-settings"></a><span data-ttu-id="afe7f-124">デバイス設定を使用する</span><span class="sxs-lookup"><span data-stu-id="afe7f-124">Using device settings</span></span>

1. <span data-ttu-id="afe7f-125">Microsoft チームルームのデバイスで、[**詳細**(**..**.)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="afe7f-125">On the Microsoft Team Rooms device, go to **More** (**...**).</span></span>
    
2. <span data-ttu-id="afe7f-126">[**設定**] を選択し、デバイス管理者のユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="afe7f-126">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="afe7f-127">[**アカウント**] タブに移動し、**先進認証**を有効にして、[**保存して終了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afe7f-127">Go to the **Account** tab, turn on **Modern Authentication**, and then select **Save and exit**.</span></span>

### <a name="using-the-xml-config-file"></a><span data-ttu-id="afe7f-128">XML 構成ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="afe7f-128">Using the XML config file</span></span>

<span data-ttu-id="afe7f-129">SkypeSettings .xml ファイルで、次のように先進認証 XML 要素を**True**に設定します。</span><span class="sxs-lookup"><span data-stu-id="afe7f-129">In your SkypeSettings.xml file, set the modern authentication XML element to **True**, as follows.</span></span>

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

<span data-ttu-id="afe7f-130">この設定を適用するには、「 [Microsoft Teams のコンソール設定を XML 構成ファイルを使ってリモートで管理](xml-config-file.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-130">To apply the setting, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

## <a name="prepare-your-environment-for-modern-authentication"></a><span data-ttu-id="afe7f-131">先進認証のために環境を準備する</span><span class="sxs-lookup"><span data-stu-id="afe7f-131">Prepare your environment for modern authentication</span></span>

<span data-ttu-id="afe7f-132">作業を始める前に、Office 365 と Azure AD で使用する id モデルを理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-132">Before you begin, make sure you understand the identity models to use with Office 365 and Azure AD.</span></span> <span data-ttu-id="afe7f-133">詳細については、「office [365 の id モデルと Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) 」および「[ハイブリッド id と office 365 のディレクトリ同期](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-133">You can find more information at [Office 365 identity models and Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) and at [Hybrid identity and directory synchronization for Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization).</span></span>

### <a name="enable-modern-authentication-in-office-365"></a><span data-ttu-id="afe7f-134">Office 365 で先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="afe7f-134">Enable modern authentication in Office 365</span></span>

<span data-ttu-id="afe7f-135">Exchange Online の先進認証を有効にするには、「 [Exchange online で先進認証を有効](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-135">To turn on modern authentication for Exchange Online, see [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span> <span data-ttu-id="afe7f-136">Skype for Business Online を使用している場合は、Skype for Business Online の先進認証が有効になっていることも確認してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-136">If you use Skype for Business Online, you should also make sure that modern authentication is turned on for Skype for Business Online.</span></span> <span data-ttu-id="afe7f-137">詳細については、「 [Skype For Business Online: 先進認証のためにテナントを有効](https://aka.ms/SkypeModernAuth)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-137">To learn more, see [Skype for Business Online: Enable your tenant for modern authentication](https://aka.ms/SkypeModernAuth).</span></span>

<span data-ttu-id="afe7f-138">Microsoft Teams の会議の設定がオンになっていて、かつ基本認証を使用するように構成されているデバイスがないことを確認する前に、Exchange Online の基本認証ポリシーを削除したり、テナントの基本認証を無効にしたりすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="afe7f-138">We recommended that you do not remove basic authentication policies for Exchange Online or disable basic authentication for your tenant before you have validated that Microsoft Teams Rooms devices can sign in to Exchange Online and Teams or Skype for Business Online successfully when the modern authentication setting is on and that there are no devices that are still configured to use basic authentication.</span></span>

<span data-ttu-id="afe7f-139">Exchange Online で基本認証を無効にする方法の詳細については、「 [Exchange online で基本認証を無効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-139">For more information about disabling basic authentication in Exchange Online, see [Disable Basic authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).</span></span>

## <a name="hybrid-modern-authentication"></a><span data-ttu-id="afe7f-140">ハイブリッド先進認証</span><span class="sxs-lookup"><span data-stu-id="afe7f-140">Hybrid modern authentication</span></span>

<span data-ttu-id="afe7f-141">オンプレミスの Exchange server や Skype for Business server への認証を成功させるには、Microsoft Teams のルームで使用されているリソースアカウントが、Azure AD から承認を取得するように構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afe7f-141">To ensure successful authentication to your on-premise Exchange server and/or Skype for Business server, you must make sure the resource account that's used with Microsoft Teams Rooms is configured to get authorization from Azure AD.</span></span> <span data-ttu-id="afe7f-142">組織に適したハイブリッド id とメソッドの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-142">To learn more about hybrid identity and methods that works for your organization, read the following topics:</span></span> 

- [<span data-ttu-id="afe7f-143">パスワードのハッシュの同期とは</span><span class="sxs-lookup"><span data-stu-id="afe7f-143">What is password hash sync?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-phs)
- [<span data-ttu-id="afe7f-144">パススルー認証とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="afe7f-144">What is passthrough authentication?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta)
- [<span data-ttu-id="afe7f-145">フェデレーションとは</span><span class="sxs-lookup"><span data-stu-id="afe7f-145">What is federation?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-fed)

### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a><span data-ttu-id="afe7f-146">Microsoft Teams のルームに固有の前提条件</span><span class="sxs-lookup"><span data-stu-id="afe7f-146">Prerequisites specific to Microsoft Teams Rooms</span></span>

<span data-ttu-id="afe7f-147">ハイブリッドトポロジでの先進認証を有効にするための前提条件は、[ハイブリッド先進認証の概要と、オンプレミスの Skype For business および Exchange server で使用するための前提条件](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="afe7f-147">The prerequisites to enable modern authentication in your hybrid topology are covered in [Hybrid modern authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview).</span></span> <span data-ttu-id="afe7f-148">この記事で説明されているすべての前提条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="afe7f-148">All the prerequisites discussed in the article apply.</span></span>

<span data-ttu-id="afe7f-149">ただし、Microsoft Teams の会議室は、[リソース所有者のパスワード](https://tools.ietf.org/html/rfc6749#section-1.3.3)認証と先進認証用の下位の REST api を使用しているため、次の重要な相違点は Microsoft Teams のルームに固有のものであるという点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-149">However, because Microsoft Teams Rooms uses [resource owner password credentials](https://tools.ietf.org/html/rfc6749#section-1.3.3) authorization and the underlying REST APIs for modern authentication, the following are important differences be aware of that are specific to Microsoft Team Rooms.</span></span>

- <span data-ttu-id="afe7f-150">Exchange server 2016 CU8 以降、または Exchange Server 2019 CU1 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="afe7f-150">You must have Exchange server 2016 CU8 or later, or Exchange Server 2019 CU1 or later.</span></span>
- <span data-ttu-id="afe7f-151">Skype for Business Server 2015 CU5 以降以降、または Skype for Business Server 2019 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="afe7f-151">You must have Skype for Business Server 2015 CU5 or later, or Skype for Business Server 2019 or later.</span></span>
- <span data-ttu-id="afe7f-152">使用しているトポロジに関係なく MFA はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="afe7f-152">MFA isn't supported regardless of the topology you have.</span></span>
- <span data-ttu-id="afe7f-153">Azure AD でサポートされているサードパーティ認証プロバイダーを使用している場合は、OAuth をサポートし、リソース所有者のパスワード認証を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afe7f-153">If you use a third-party authentication provider that's supported by Azure AD, it must support OAuth and use  resource owner password credentials authorization.</span></span>
- <span data-ttu-id="afe7f-154">アプリケーションで構成されているリソースアカウントに対して、デバイスレベルの条件付きアクセスポリシーは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-154">Do not use device-level conditional access policies for a resource account configured with the application.</span></span> <span data-ttu-id="afe7f-155">この操作を行うと、サインインエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="afe7f-155">Doing so will result in sign-in failures.</span></span> <span data-ttu-id="afe7f-156">代わりに、[ここ](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess)で説明したガイダンスを使用して、Microsoft Intune にデバイスを登録して、コンプライアンスポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="afe7f-156">Instead, enroll a device in Microsoft Intune and apply compliance policies by using the guidance published [here](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).</span></span>

### <a name="configure-exchange-server"></a><span data-ttu-id="afe7f-157">Exchange Server の構成</span><span class="sxs-lookup"><span data-stu-id="afe7f-157">Configure Exchange Server</span></span>

<span data-ttu-id="afe7f-158">Exchange Server でハイブリッド先進認証を有効にするには、「[オンプレミスの Exchange Server でハイブリッド先進認証を使用するように構成する方法](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-158">To enable hybrid modern authentication in Exchange Server, see [How to configure Exchange Server on-premises to use hybrid modern authentication](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).</span></span>

### <a name="configure-skype-for-business-server"></a><span data-ttu-id="afe7f-159">Skype for Business Server を構成する</span><span class="sxs-lookup"><span data-stu-id="afe7f-159">Configure Skype for Business Server</span></span>

<span data-ttu-id="afe7f-160">Skype for Business Server とのハイブリッド先進認証を有効にするには、「[ハイブリッド先進認証を使用するように skype For business をオンプレミスで構成する方法](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-160">To enable hybrid modern authentication with Skype for Business Server, see [How to configure Skype for Business on-premises to use hybrid modern authentication](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).</span></span>

### <a name="remove-or-disable-skype-for-business-and-exchange"></a><span data-ttu-id="afe7f-161">Skype for Business および Exchange を削除または無効にする</span><span class="sxs-lookup"><span data-stu-id="afe7f-161">Remove or disable Skype for Business and Exchange</span></span>

<span data-ttu-id="afe7f-162">セットアップでハイブリッド先進認証が許可されていない場合、または Exchange または Skype for Business のハイブリッド先進認証を削除または無効にする必要がある場合は、「 [Skype For business および exchange からのハイブリッド先進認証の削除または無効化](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-162">If your setup doesn't allow for hybrid modern authentication or you need to remove or disable hybrid modern authentication for Exchange or Skype for Business, see [Removing or disabling hybrid modern authentication from Skype for Business and Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).</span></span>

### <a name="azure-ad-conditional-access"></a><span data-ttu-id="afe7f-163">Azure AD の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="afe7f-163">Azure AD conditional access</span></span>

<span data-ttu-id="afe7f-164">Microsoft Teams のルームで使用されるリソースアカウントを、IP/場所ベースのアクセスに対して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="afe7f-164">You can configure a resource account used with Microsoft Teams Rooms for IP/location-based access.</span></span> <span data-ttu-id="afe7f-165">詳細については、「[条件付きアクセス: 場所でのアクセスをブロック](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-165">To learn more, see [Conditional Access: Block access by location](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location).</span></span>

<span data-ttu-id="afe7f-166">その他の条件付きアクセスポリシーはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="afe7f-166">No other conditional access policies are supported.</span></span> <span data-ttu-id="afe7f-167">デバイスのコンプライアンスの詳細については、[こちら](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess)のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe7f-167">For more information about device compliance, see the guidance  [here](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).</span></span>  