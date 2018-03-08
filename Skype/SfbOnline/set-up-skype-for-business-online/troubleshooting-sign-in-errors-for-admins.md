---
title: "管理者向けの Skype を Business Online サインイン エラーのトラブルシューティング"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "これらの問題のトラブルシューティングを行って Skype for Business Online のサインイン エラーと作業の一般的な原因を説明します。 "
ms.openlocfilehash: aa5069e5fd5bf40ebd460c03b72ce8d9327da6d2
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a><span data-ttu-id="32fb5-103">管理者向けの Skype を Business Online サインイン エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="32fb5-103">Troubleshooting Skype for Business Online sign-in errors for administrators</span></span>

<span data-ttu-id="32fb5-p101">Skype for Business Online サインイン エラーのトラブルシューティングにまずへのサインインに問題の一般的な原因を除去します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p101">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty. If necessary, you can then follow specific resolution steps based on the type of error. If the user still cannot sign in, collect additional information, and then seek additional help.</span></span> 
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="32fb5-107">目的に合ったトピックをクリックしてください</span><span class="sxs-lookup"><span data-stu-id="32fb5-107">What do you want to do?</span></span>
<span data-ttu-id="32fb5-108"><a name="top"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-108"></span></span>

> [<span data-ttu-id="32fb5-109">Skype for Business Online サインイン エラーの一般的な原因をチェックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-109">Check for common causes of Skype for Business Online sign-in errors</span></span>](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
    
> [<span data-ttu-id="32fb5-110">特定のエラー (エンタープライズのみ) の解決手順に従う</span><span class="sxs-lookup"><span data-stu-id="32fb5-110">Follow resolution steps for a specific error (Enterprise only)</span></span>](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
    
> [<span data-ttu-id="32fb5-111">Msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-111">Add a firewall entry for msoidsvc.exe to your proxy server</span></span>](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
    
> [<span data-ttu-id="32fb5-112">DNS の設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-112">Update DNS settings</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
    
> [<span data-ttu-id="32fb5-113">サード パーティの SSL 証明書を ADFS サーバー上にインストールします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-113">Install a third-party SSL certificate on your ADFS server</span></span>](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
    
> [<span data-ttu-id="32fb5-114">セキュリティ資格情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-114">Update security credentials</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
    
> [<span data-ttu-id="32fb5-115">TrustModelData レジストリ キーを変更します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-115">Modify TrustModelData registry keys</span></span>](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
    
> [<span data-ttu-id="32fb5-116">Active Directory でユーザー設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-116">Update user settings in Active Directory</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
    
> [<span data-ttu-id="32fb5-117">Microsoft サポートのトラブルシューティング ガイドを使う</span><span class="sxs-lookup"><span data-stu-id="32fb5-117">Use the Microsoft Support troubleshooting guide</span></span>](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
    
> [<span data-ttu-id="32fb5-118">詳細情報を収集し、その他のヘルプを探す.</span><span class="sxs-lookup"><span data-stu-id="32fb5-118">Collect more information and seek additional help </span></span>](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)
    
## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a><span data-ttu-id="32fb5-119">Skype for Business Online サインイン エラーの一般的な原因をチェックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-119">Check for common causes of Skype for Business Online sign-in errors</span></span>
<span data-ttu-id="32fb5-120"><a name="toc323194094"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-120"></span></span>

<span data-ttu-id="32fb5-p102">少数の原因が考えのほとんどのサインインに関する問題の原因し、これらの多くは簡単に修正します。次の表は、サインイン エラーの一般的な原因とその解決するか、ユーザーがかかることがいくつかの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p102">Most sign-in issues can be traced to a small number of causes, and many of these are easy to correct. The table below lists some common causes of sign-in errors and some steps you or the users can take to resolve them.</span></span>
  
|<span data-ttu-id="32fb5-123">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="32fb5-123">**Possible Cause**</span></span>|<span data-ttu-id="32fb5-124">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="32fb5-124">**Resolution**</span></span>|
|:-----|:-----|
|<span data-ttu-id="32fb5-125">サインイン時にダイアログ ボックスが表示語句を含む:**が、サーバーがある、サインイン アドレスに対して信頼されていることを確認することはできません。接続しますか?**</span><span class="sxs-lookup"><span data-stu-id="32fb5-125">During sign-in, a dialog box appears that contains the following phrase: **cannot verify that the server is trusted for your sign-in address. Connect anyway?**</span></span> <br/> |<span data-ttu-id="32fb5-126">ダイアログ ボックスで、ドメイン名に、組織内の信頼されたサーバーがあることを確認、たとえば、 **domainName.contoso.com**します。**常にこのサーバーを信頼する**] チェック ボックスをオンにユーザーに確認し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-126">Verify that the domain name in the dialog box is a trusted server in your organization—for example, **domainName.contoso.com**. Ask the user to select the **Always trust this server** check box, and then click **Connect**.</span></span> <br/> <span data-ttu-id="32fb5-p103">企業のお客様は、このメッセージをされたユーザーが各ユーザーのコンピューターで Windows レジストリを編集して、1 回サインインしたときに表示されないようにします。詳細については、[変更 TrustModelData レジストリ キー](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p103">Enterprise customers can prevent this message from appearing when a user signs in for the first time by modifying the Windows registry on each user's computer. For details, see [Modify TrustModelData registry keys](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).</span></span><br/> |
|<span data-ttu-id="32fb5-129">サインイン アドレス、ユーザー名、またはパスワードの入力が誤っています</span><span class="sxs-lookup"><span data-stu-id="32fb5-129">Mistyped sign-in address, user name, or password</span></span>  <br/> | <span data-ttu-id="32fb5-130">ユーザーのサインイン名とパスワードが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-130">Confirm that the user's sign-in name and password are correct.</span></span> <br/>  <span data-ttu-id="32fb5-131">ユーザーのサインイン名が次のように書式設定されたことを確認する: **bobk@contoso.com**します。組織のネットワークへのサインインに使用する書式と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="32fb5-131">Verify that the user's sign-in name is formatted as follows: **bobk@contoso.com**. This may be different from the format you use to sign in to your organization's network.</span></span>  <br/>  <span data-ttu-id="32fb5-132">もう一度サインインをユーザーに依頼します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-132">Ask the user to try signing in again.</span></span> <br/> |
|<span data-ttu-id="32fb5-133">パスワードを忘れました</span><span class="sxs-lookup"><span data-stu-id="32fb5-133">Forgotten password</span></span>  <br/> |<span data-ttu-id="32fb5-134">ユーザーのパスワードを再設定し、新しい一時的なパスワードに通知します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-134">Reset the user's password and notify him or her of the new temporary password.</span></span>  <br/> |
|<span data-ttu-id="32fb5-135">Skype for Business Online を使用ライセンスがありません。</span><span class="sxs-lookup"><span data-stu-id="32fb5-135">Not licensed to use Skype for Business Online</span></span>  <br/> |<span data-ttu-id="32fb5-p104">ユーザーが Skype for Business Online ユーザーとして登録されていることを確認します。されない場合は、ユーザーを登録し、またはをもう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p104">Confirm that the user is registered as a Skype for Business Online user. If not, register the user, and then ask him or her to sign in again.</span></span>  <br/> |
|<span data-ttu-id="32fb5-138">Skype for Business Online がインストールされているバージョンが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="32fb5-138">Wrong version of Skype for Business Online installed</span></span>  <br/> |<span data-ttu-id="32fb5-139">この問題は通常、次の語句を含むエラー メッセージに関連付けられて:**認証サービスがこのバージョンのプログラムと互換性があります**。</span><span class="sxs-lookup"><span data-stu-id="32fb5-139">This issue is usually associated with an error message that contains the following phrase: **the authentication service may be incompatible with this version of the program**.</span></span>  <br/> <span data-ttu-id="32fb5-140">アンインストールして、Skype を for Business Online、Office 365 ポータルから再インストールするユーザーに依頼します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-140">Ask the user to uninstall and reinstall Skype for Business Online from the Office 365 Portal.</span></span>  <br/> |
|<span data-ttu-id="32fb5-141">サインインに必要な個人証明書を取得する際に問題があります</span><span class="sxs-lookup"><span data-stu-id="32fb5-141">Problem acquiring a personal certificate that is required to sign in</span></span>  <br/> |<span data-ttu-id="32fb5-p105">ユーザーのサインイン アドレスが最近変更された場合は、キャッシュされたサインイン用のデータを削除する必要があります。サインアウトして、サインイン情報へのサインイン画面で、リンクから、やり直しての削除] をクリックしてもらいます。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p105">If the user's sign-in address has recently changed, they may need to delete cached sign-in data. Ask users to sign out, click the Delete my sign-in info link on the sign-in screen, and then try again.</span></span>  <br/> |
|<span data-ttu-id="32fb5-144">カスタム ドメイン名をセットアップしていますが、変更内容がシステムに反映し終わっていない場合があります</span><span class="sxs-lookup"><span data-stu-id="32fb5-144">You set up a custom domain name, and the changes may not have finished propagating through the system.</span></span>  <br/> |<span data-ttu-id="32fb5-145">最初に、変更を反映するようにドメイン名サービス (DNS) レコードが変更されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-145">First, ensure that you have modified the Domain Name Service (DNS) records to reflect the change.</span></span>  <br/> <span data-ttu-id="32fb5-p106">既に DNS に必要な変更をした場合は、後でログインするようユーザーに通知します。DNS の変更は、システム全体に反映するため 72 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p106">If you have already made the necessary DNS changes, advise the user to try logging in later. DNS changes can take up to 72 hours to be reflected throughout the system.</span></span>  <br/> |
|<span data-ttu-id="32fb5-148">システム クロックがサーバー クロックと同期していません</span><span class="sxs-lookup"><span data-stu-id="32fb5-148">System clock out of sync with server clock</span></span>  <br/> |<span data-ttu-id="32fb5-p107">信頼性の高い外部タイム ソースと、ネットワークのドメイン コント ローラーが同期されることを確認します。詳細については、Microsoft サポート技術情報の記事 816042、 [Windows Server で時間を優先するサーバーを構成する方法](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p107">Ensure that your network domain controller is synchronizing with a reliable external time source. For details, see the Microsoft Knowledge Base article 816042, [How to configure an authoritative time server in Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).</span></span><br/> |
   
<span data-ttu-id="32fb5-p108">Skype for Business Online サインイン エラーのトラブルシューティングにまずへのサインインに問題の一般的な原因を除去します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p108">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty. If necessary, you can then follow specific resolution steps based on the type of error. If the user still cannot sign in, collect additional information, and then seek additional help.</span></span> 
  
## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a><span data-ttu-id="32fb5-154">特定のエラーの解決手順に従う (エンタープライズのみ)</span><span class="sxs-lookup"><span data-stu-id="32fb5-154">Follow resolution steps for a specific error (Enterprise only)</span></span>
<span data-ttu-id="32fb5-155"><a name="toc325626440"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-155"></span></span>

> [!IMPORTANT]
>  <span data-ttu-id="32fb5-p109">次の手順は、Microsoft Office 365 プラン E の顧客の主な目的としています。Office 365 プラン P 製品を使用している場合は、[詳細情報を収集しその他のヘルプを探す. ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)、次のセクションに進みます。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p109">These instructions are intended primarily for Microsoft Office 365 Plan E customers. If you are an Office 365 Plan P customer, continue to the following section,[Collect more information and seek additional help ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).</span></span> 
  
<span data-ttu-id="32fb5-p110">ユーザーは、前のセクションの提案を実施した後にサインインできない場合、は、エラーの種類に基づいて、その他のトラブルシューティングを実行できます。次の表は、最も一般的なエラー メッセージと考えられる原因を示します。各問題を解決する手順の詳細については、次の表。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p110">If the user cannot sign in after you have tried the suggestions in the previous section, then you can do additional troubleshooting based on the type of error. The table below lists the most common error messages and possible causes. Following the table are detailed procedures to address each issue.</span></span>
  
|<span data-ttu-id="32fb5-161">**エラー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="32fb5-161">**Error message**</span></span>|<span data-ttu-id="32fb5-162">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="32fb5-162">**Possible cause**</span></span>|<span data-ttu-id="32fb5-163">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="32fb5-163">**Resolution**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="32fb5-164">サインイン アドレスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="32fb5-164">Sign-in address not found</span></span>  <br/> |<span data-ttu-id="32fb5-165">Microsoft Online Services サインイン アシスタントからのサインイン要求 (msoidsvc.exe) が、外部ファイアウォール、またはプロキシ サーバーを通っていません。</span><span class="sxs-lookup"><span data-stu-id="32fb5-165">Sign-in requests from the Microsoft Online Services Sign-On Assistant (msoidsvc.exe) are not going through your external firewall, or proxy server.</span></span>  <br/> |[<span data-ttu-id="32fb5-166">Msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-166">Add a firewall entry for msoidsvc.exe to your proxy server</span></span>](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|<span data-ttu-id="32fb5-167">サーバーが一時的に利用できません</span><span class="sxs-lookup"><span data-stu-id="32fb5-167">Server is temporarily unavailable</span></span>  <br/> |<span data-ttu-id="32fb5-168">組織でカスタム ドメインを使用している場合、必要なドメイン ネーム システム (DNS:Domain Name System) が見つからない、または正しくない場合があります。</span><span class="sxs-lookup"><span data-stu-id="32fb5-168">If your organization has a custom domain, the necessary Domain Name System (DNS) settings may be missing or incorrect.</span></span>  <br/> |[<span data-ttu-id="32fb5-169">DNS の設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-169">Update DNS settings</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|<span data-ttu-id="32fb5-170">サーバーが一時的に利用できません</span><span class="sxs-lookup"><span data-stu-id="32fb5-170">Server is temporarily unavailable</span></span>  <br/> |<span data-ttu-id="32fb5-171">Active Directory フェデレーション サービス (ADFS) によるシングル サインオンを使用している組織では、サード パーティの証明機関からの証明書ではなく、自己署名された Secure Socket Layer (SSL) 証明書を使用していた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32fb5-171">If your organization is using single sign-on with Active Directory Federation Services (ADFS), you may have used a self-signed Secure Socket Layer (SSL) certificate rather than one from a third-party certification authority.</span></span>  <br/> |[<span data-ttu-id="32fb5-172">サード パーティの SSL 証明書を ADFS サーバー上にインストールします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-172">Install a third-party SSL certificate on your ADFS server</span></span>](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|<span data-ttu-id="32fb5-173">サインインに必要な個人証明書を取得する際に問題があります</span><span class="sxs-lookup"><span data-stu-id="32fb5-173">Problem acquiring a personal certificate that is required to sign in</span></span>  <br/> |<span data-ttu-id="32fb5-174">既に削除した場合キャッシュされたサーバー データを使用してサインイン エラーが引き続き表示される、ユーザーのセキュリティ資格情報が破損している可能性がありますが、やユーザーのコンピューターの RSA フォルダーでは認証がブロックされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32fb5-174">If you've already removed the cached server data used to sign in and the error continues to appear, the user's security credentials may be corrupted, or an RSA folder on the user's computer may be blocking authentication.</span></span>  <br/> |[<span data-ttu-id="32fb5-175">セキュリティ資格情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-175">Update security credentials</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|<span data-ttu-id="32fb5-176">ユーザーが初めてサインインするときは、証明書を承認するためのダイアログ ボックスが表示されます</span><span class="sxs-lookup"><span data-stu-id="32fb5-176">A certificate trust dialog box appears when a user signs in for the first time.</span></span>  <br/> |<span data-ttu-id="32fb5-177">Skype for Business サーバーが**TrustModelData**レジストリ キーにまだ追加されていない場合は、このダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32fb5-177">This dialog box appears if your Skype for Business server is not yet listed in the **TrustModelData** registry key.</span></span> <br/> |[<span data-ttu-id="32fb5-178">TrustModelData レジストリ キーを変更します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-178">Modify TrustModelData registry keys</span></span>](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|<span data-ttu-id="32fb5-179">ユーザーに対して SIP が有効ではありません</span><span class="sxs-lookup"><span data-stu-id="32fb5-179">User is not SIP enabled</span></span>  <br/> |<span data-ttu-id="32fb5-p111">組織には、Microsoft Office Communications Server または Microsoft Lync Server 2010 の以前のインストールがある、可能性がありますいないから削除したユーザー サーバー解除にする前にします。その結果**に UserEnabled**属性**FALSE** Active Directory ドメイン サービスの設定が。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p111">If your organization had a previous installation of Microsoft Office Communications Server or Microsoft Lync Server 2010, you may not have deleted your users from the server before decommissioning it. As a result, the **msRTCSIP-UserEnabled** attribute is still set to **FALSE** in Active Directory Domain Services. </span></span><br/> |[<span data-ttu-id="32fb5-182">Active Directory でユーザー設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-182">Update user settings in Active Directory</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |
   
### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a><span data-ttu-id="32fb5-183">msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します</span><span class="sxs-lookup"><span data-stu-id="32fb5-183">Add a firewall entry for msoidsvc.exe to your proxy server</span></span>
<span data-ttu-id="32fb5-184"><a name="add-a-firewall"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-184"></span></span>

<span data-ttu-id="32fb5-185">この手順は次のエラー メッセージに対して考えられる修正:**サインイン アドレスは見つかりませんでした**。</span><span class="sxs-lookup"><span data-stu-id="32fb5-185">This procedure is a possible fix for the following error message: **Sign-in address not found**.</span></span>
  
 <span data-ttu-id="32fb5-p112">**メモ**: 次の手順では、Microsoft Forefront 脅威 Management Gateway (TMG) 2010 を使用するいると仮定します。別の web ゲートウェイ ソリューションを使っている場合は、以下の手順 4 で説明する、設定を使います。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p112">**NOTE**: The following steps assume you are using Microsoft Forefront Threat Management Gateway (TMG) 2010. If you have a different web gateway solution, use the settings described in step 4 below.</span></span>
  
<span data-ttu-id="32fb5-188">Forefront TMG 2010 で Msoidsvc.exe のアプリケーション エントリを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-188">To create an application entry for Msoidsvc.exe in Forefront TMG 2010, follow these steps:</span></span>
  
1. <span data-ttu-id="32fb5-189">Forefront の左側のウィンドウで [**ネットワーク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-189">In the Forefront left pane, click **Networking**.</span></span>
    
2. <span data-ttu-id="32fb5-190">[**ネットワーク**] タブをクリックします。右側のウィンドウで [**タスク**] タブで、[ **Forefront TMG クライアント設定の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-190">Click the **Network** tab. Under the **Tasks** tab in the right pane, click **Configure Forefront TMG Client Settings**.</span></span>
    
3. <span data-ttu-id="32fb5-191">**Forefront TMG クライアント設定**] ダイアログ ボックスで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-191">In the **Forefront TMG Client Settings** dialog box, click **New**.</span></span>
    
4. <span data-ttu-id="32fb5-192">**アプリケーション エントリの設定**] ダイアログ ボックスで、次のルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-192">In the **Application Entry Setting** dialog box, configure the following rules:</span></span>
    
|<span data-ttu-id="32fb5-193">**アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="32fb5-193">**Application**</span></span>|<span data-ttu-id="32fb5-194">**キー**</span><span class="sxs-lookup"><span data-stu-id="32fb5-194">**Key**</span></span>|<span data-ttu-id="32fb5-195">**{Value}**</span><span class="sxs-lookup"><span data-stu-id="32fb5-195">**Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="32fb5-196">**msoidsvc**</span><span class="sxs-lookup"><span data-stu-id="32fb5-196">**msoidsvc**</span></span> <br/> |<span data-ttu-id="32fb5-197">Disable</span><span class="sxs-lookup"><span data-stu-id="32fb5-197">Disable</span></span>  <br/> |<span data-ttu-id="32fb5-198">0</span><span class="sxs-lookup"><span data-stu-id="32fb5-198">0</span></span>  <br/> |
|<span data-ttu-id="32fb5-199">**msoidsvc**</span><span class="sxs-lookup"><span data-stu-id="32fb5-199">**msoidsvc**</span></span> <br/> |<span data-ttu-id="32fb5-200">DisableEx</span><span class="sxs-lookup"><span data-stu-id="32fb5-200">DisableEx</span></span>  <br/> |<span data-ttu-id="32fb5-201">0</span><span class="sxs-lookup"><span data-stu-id="32fb5-201">0</span></span>  <br/> |
   
<span data-ttu-id="32fb5-202">詳細について[をオンプレミスのファイアウォールが接続をブロックするために、Skype for Business Online に接続できない](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)Microsoft サポート技術情報の記事 2409256「を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-202">For details, see the Microsoft Knowledge Base article 2409256, [You cannot connect to Skype for Business Online because an on-premises firewall blocks the connection](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).</span></span>
  
### <a name="update-dns-settings"></a><span data-ttu-id="32fb5-203">DNS 設定を更新する</span><span class="sxs-lookup"><span data-stu-id="32fb5-203">Update DNS settings</span></span>
<span data-ttu-id="32fb5-204"><a name="update-dns-service"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-204"></span></span>

<span data-ttu-id="32fb5-205">組織にカスタム ドメインがある場合は、この手順は、次のエラー メッセージに対して考えられる修正:**サーバーが一時的に利用できません**。</span><span class="sxs-lookup"><span data-stu-id="32fb5-205">If your organization has a custom domain, this procedure is a possible fix for the following error message: **Server is temporarily unavailable**.</span></span>
  
- <span data-ttu-id="32fb5-206">次の CNAME レコードをドメインに追加する方法については、ドメイン名レジストラーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-206">Contact your domain name registrar for information on how to add the following CNAME record to your domain:</span></span>
    
  - <span data-ttu-id="32fb5-207">**DNS レコードの種類**: CNAME</span><span class="sxs-lookup"><span data-stu-id="32fb5-207">**DNS record type**: CNAME</span></span> 
    
  - <span data-ttu-id="32fb5-208">**名前**: sip</span><span class="sxs-lookup"><span data-stu-id="32fb5-208">**Name**: sip</span></span>
    
  - <span data-ttu-id="32fb5-209">**値/先**: sipdir.online.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="32fb5-209">**Value/Destination**: sipdir.online.microsoft.com</span></span>
    
<span data-ttu-id="32fb5-210">詳細については、Microsoft サポート技術情報の記事 2566790「 [Office 365 でビジネス Online DNS 構成の問題のトラブルシューティング Skype](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-210">For details, see the Microsoft Knowledge Base article 2566790, [Troubleshooting Skype for Business Online DNS configuration issues in Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).</span></span>
  
### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a><span data-ttu-id="32fb5-211">サード パーティの SSL 証明書を ADFS サーバー上にインストールします</span><span class="sxs-lookup"><span data-stu-id="32fb5-211">Install a third-party SSL certificate on your ADFS server</span></span>
<span data-ttu-id="32fb5-212"><a name="verify-upn-and"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-212"></span></span>

<span data-ttu-id="32fb5-213">Active Domain Federation Services (ADFS) サーバーにサード パーティの SSL 証明書をインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-213">To install a third-party SSL certificate on your Active Domain Federation Services (ADFS) server, follow these steps:</span></span>
  
1. <span data-ttu-id="32fb5-214">サードパーティの証明機関 (VeriSign や Thawte など) から SSL 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-214">Obtain an SSL certificate from a third-party certification authority such as VeriSign or Thawte.</span></span>
    
2. <span data-ttu-id="32fb5-215">証明書を ADFS サーバー上 ADFS 管理コンソールを使用してインストールします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-215">Install the certificate on your ADFS server by using the ADFS management console.</span></span> 
    
### <a name="update-security-credentials"></a><span data-ttu-id="32fb5-216">セキュリティ資格情報を更新する</span><span class="sxs-lookup"><span data-stu-id="32fb5-216">Update security credentials</span></span>
<span data-ttu-id="32fb5-217"><a name="update-security-credentials"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-217"></span></span>

<span data-ttu-id="32fb5-218">この手順は、エラー メッセージ**のサインインに必要な個人証明書を取得する際に問題**の考えられる修正です。</span><span class="sxs-lookup"><span data-stu-id="32fb5-218">This procedure is a possible fix for the error message **Problem acquiring a personal certificate required to sign in**.</span></span>
  
<span data-ttu-id="32fb5-p113">証明書または資格情報の可能性のある問題を消すために最初に、ユーザーの証明書では、Windows 証明書を更新します。これを行うには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p113">To eliminate possible certificate or credential problems, first renew the user's certificate in Windows Certificate Manager. To do this, follow these steps:</span></span>
  
1. <span data-ttu-id="32fb5-p114">Windows の証明書マネージャーを開きます。これを行うには、[**スタート**] ボタン**実行**] をクリックして、 **certmgr.msc**] と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p114">Open Windows Certificate Manager. To do this, click **Start**, click **Run**, type **certmgr.msc**, and then click **OK**.</span></span> 
    
2. <span data-ttu-id="32fb5-223">**個人**をダブルクリックし、[**証明書**をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-223">Double-click **Personal**, and then double-click **Certificates**.</span></span> 
    
3. <span data-ttu-id="32fb5-224">**[発行先**] 列、Communications Server が発行した証明書を確認して並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="32fb5-224">Sort by the **Issued By** column, and then look for a certificate that is issued by Communications Server.</span></span>
    
4. <span data-ttu-id="32fb5-225">証明書を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-225">Right-click the certificate, and then click **Delete**.</span></span> 
    
<span data-ttu-id="32fb5-p115">次に、Windows 7 を実行している場合は、Windows 資格情報マネージャーで、格納されている資格情報を削除します。これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p115">Next, if the user is running Windows 7, remove their stored credentials in Windows Credential Manager. To do this, follow these steps:</span></span>
  
1. <span data-ttu-id="32fb5-228">[**スタート**] ボタン、**コントロール パネル**] をクリックし、[**資格情報マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-228">Click **Start**, click **Control Panel**, and then click **Credential Manager**.</span></span> 
    
2. <span data-ttu-id="32fb5-229">Skype for Business Online に接続するための資格情報のセットを見つけます。</span><span class="sxs-lookup"><span data-stu-id="32fb5-229">Locate the set of credentials that is used to connect to Skype for Business Online.</span></span> 
    
3. <span data-ttu-id="32fb5-230">資格情報のセットを展開し、**コンテナーから削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-230">Expand the set of credentials, and then click **Remove from Vault**.</span></span> 
    
4. <span data-ttu-id="32fb5-231">もう一度サインインし、ユーザーの資格情報を再入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-231">Sign in again and reenter the user's credentials.</span></span>
    
<span data-ttu-id="32fb5-232">最後に、ユーザーもサインインできない場合、資格情報を更新した後、試してくださいユーザーのコンピューターの RSA フォルダーを削除するため、ユーザーの認証プロセスの実行がブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32fb5-232">Finally, if the user still cannot sign in after you've updated their credentials, try deleting the RSA folder on the user's computer, because it could be blocking completion of the user authentication process:</span></span>
  
1. <span data-ttu-id="32fb5-233">管理者アカウントを使用して、ユーザーのコンピューターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-233">Sign in to the user's computer using an administrator account.</span></span>
    
2. <span data-ttu-id="32fb5-234">必要に応じて、**非表示のファイルを表示する**フォルダーの表示オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-234">If necessary, turn on the folder view option **Show hidden files**.</span></span> 
    
3. <span data-ttu-id="32fb5-235">次に、アドレス バー エクスプ ローラーの入力: **c:\\ドキュメントと設定\\ユーザー名\\アプリケーション データ\\Microsoft\\暗号化\\RSA**、***ユーザー名***には、Windows のサインイン名です。</span><span class="sxs-lookup"><span data-stu-id="32fb5-235">Type the following into the address bar of File Explorer: **C:\\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**, where ***UserName*** is your Windows sign-in name.</span></span>
    
4. <span data-ttu-id="32fb5-236">名前で始まり、任意のフォルダーを削除する**S-1-5-21 -**数字のストリングが続きます。</span><span class="sxs-lookup"><span data-stu-id="32fb5-236">Delete any folder that begins with the name **S-1-5-21-** followed by a string of numbers.</span></span>
    
### <a name="modify-trustmodeldata-registry-keys"></a><span data-ttu-id="32fb5-237">TrustModelData レジストリ キーを変更する</span><span class="sxs-lookup"><span data-stu-id="32fb5-237">Modify TrustModelData registry keys</span></span>
<span data-ttu-id="32fb5-238"><a name="modify-trustmodeldata-registry"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-238"></span></span>

<span data-ttu-id="32fb5-p116">ユーザーが初めてサインインすると、次のようなものが含まれているダイアログ ボックスが表示があります:**が、サーバーがある、サインイン アドレスに対して信頼されていることを確認することはできません。接続しますか?**これは、セキュリティ機能、およびエラーではありません。ただし、することができます] ダイアログ ボックスが表示されないようにグループ ポリシー オブジェクト (GPO) を使用して、1 回サインインする前に、ドメイン名をユーザーのコンピューターを更新します。これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p116">When a user signs in for the first time, they may receive a dialog box that contains something like the following: **Cannot verify that the server is trusted for your sign-in address. Connect anyway?** This is a security feature, and not an error. However, you can prevent the dialog box from appearing by using a Group Policy Object (GPO) to update users' machines with your domain name before they sign in for the first time. To accomplish this, do the following:</span></span>
  
- <span data-ttu-id="32fb5-243">作成して、Skype for Business のドメイン名を付加する GPO を展開する-domainName.contoso.com—to HKEY_LOCAL_MACHINE の現在の値など、\\ソフトウェア\\ポリシー\\Microsoft\\Communicator\\TrustModelData します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-243">Create and deploy a GPO that appends your Skype for Business domain name—for example, domainName.contoso.com—to the current value of HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="32fb5-244">必要な*追加*既存の値にドメイン名を置き換えるだけでなくします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-244">You must *append*  your domain name to the existing value, not simply replace it.</span></span>
  
<span data-ttu-id="32fb5-245">詳細については、 [Skype for Business (Lync) のサーバーが、サインイン アドレスに対して信頼されていることを確認できない](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)Microsoft サポート技術情報の記事 2531068「、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-245">For details, see the Microsoft Knowledge Base article 2531068, [Skype for Business (Lync) cannot verify that the server is trusted for your sign-in address](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).</span></span>
  
### <a name="update-user-settings-in-active-directory"></a><span data-ttu-id="32fb5-246">Active Directory のユーザー設定を更新する</span><span class="sxs-lookup"><span data-stu-id="32fb5-246">Update user settings in Active Directory</span></span>
<span data-ttu-id="32fb5-247"><a name="update-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-247"></span></span>

<span data-ttu-id="32fb5-p117">組織には、Microsoft Office Communications Server または Microsoft Lync Server 2010 の以前のインストールがある、可能性がありますいないから削除したユーザー サーバー解除にする前にします。その結果**に UserEnabled**属性**FALSE** Active Directory ドメイン サービスの設定が。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p117">If your organization had a previous installation of Microsoft Office Communications Server or Microsoft Lync Server 2010, you may not have deleted your users from the server before decommissioning it. As a result, the **msRTCSIP-UserEnabled** attribute is still set to **FALSE** in Active Directory Domain Services.</span></span>
  
<span data-ttu-id="32fb5-250">この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-250">To fix this issue, follow these steps:</span></span>
  
1. <span data-ttu-id="32fb5-251">影響を受けるすべてのユーザー**に UserEnabled**属性を**TRUE**に更新します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-251">Update the **msRTCSIP-UserEnabled** attribute for all affected users to **TRUE**.</span></span>
    
2. <span data-ttu-id="32fb5-p118">Microsoft Online Services ディレクトリ同期ツール (DirSync) を再実行します。詳細については、 [AIntegrate 社内に Azure Active Directory ディレクトリ](https://technet.microsoft.com/en-us/library/hh967642.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p118">Rerun the Microsoft Online Services Directory Synchronization Tool (DirSync). For details, see [AIntegrate your on-premises directories with Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).</span></span> 
    
<span data-ttu-id="32fb5-p119">Skype for Business Online サインイン エラーのトラブルシューティングにまずへのサインインに問題の一般的な原因を除去します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p119">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty. If necessary, you can then follow specific resolution steps based on the type of error. If the user still cannot sign in, collect additional information, and then seek additional help.</span></span> 
## <a name="use-the-microsoft-support-troubleshooting-guide"></a><span data-ttu-id="32fb5-257">Microsoft サポートのトラブルシューティング ガイドを使う</span><span class="sxs-lookup"><span data-stu-id="32fb5-257">Use the Microsoft Support troubleshooting guide</span></span>
<span data-ttu-id="32fb5-258"><a name="toc325626447"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-258"></span></span>

<span data-ttu-id="32fb5-259">ユーザーのサインインの問題を解決するのにはまだできない場合は、Microsoft サポート技術情報の記事 2541980「、 [Skype for Business Online のサインインに関する問題をトラブルシューティングする方法](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)の提案を確認します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-259">If you're still not able to resolve the user's sign-in problems, review the suggestions in Microsoft Knowledge Base article 2541980, [How to troubleshoot sign-in issues in Skype for Business Online](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).</span></span>
  
## <a name="collect-more-information-and-seek-additional-help"></a><span data-ttu-id="32fb5-260">詳細情報を収集し、ヘルプを探す</span><span class="sxs-lookup"><span data-stu-id="32fb5-260">Collect more information and seek additional help</span></span>
<span data-ttu-id="32fb5-261"><a name="collect-more-information"> </a></span><span class="sxs-lookup"><span data-stu-id="32fb5-261"></span></span>

<span data-ttu-id="32fb5-p120">場合は、上記のガイダンスを実行しても、サインインに関する問題を解決できない、その他の情報を収集し、テクニカル サポートにお問い合わせください。これを行うには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p120">If you've followed the guidance above and still can't resolve your sign-in issues, you must collect additional information and contact technical support. To do this, follow these steps:</span></span> 
  
1. <span data-ttu-id="32fb5-p121">ユーザーのコンピューターから、ログ ファイルと Windows イベント ログの詳細を取得します。詳しい手順については、 [Lync でのエラー ログを有効にする](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)エンド ユーザー ヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p121">Obtain the log files and Windows Event log details from the user's machine. For step-by-step instructions, see the end-user help topic [Turn on error logs in Lync](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).</span></span>
    
2. <span data-ttu-id="32fb5-266">ログ ファイル、およびエラーに関する詳細情報を Microsoft テクニカル サポートにお送りください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-266">Send the log files and detailed information about the error to Microsoft technical support.</span></span>
    
<span data-ttu-id="32fb5-p122">影響を受けるユーザーのコンピューターで、Microsoft Online Services Diagnostic and Logging (MOSDAL) サポート ツールキットをインストールして、追加の診断情報を指定するを求められる場合があります。詳細については、「 [MOSDAL サポート ツールキット](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p122">You may be asked to supply additional diagnostic information by installing the Microsoft Online Services Diagnostic and Logging (MOSDAL) Support Toolkit on the affected user's machine. For details, see [Using the MOSDAL Support Toolkit](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).</span></span>
  
<span data-ttu-id="32fb5-p123">Skype for Business Online サインイン エラーのトラブルシューティングにまずへのサインインに問題の一般的な原因を除去します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。</span><span class="sxs-lookup"><span data-stu-id="32fb5-p123">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty. If necessary, you can then follow specific resolution steps based on the type of error. If the user still cannot sign in, collect additional information, and then seek additional help.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="32fb5-272">関連トピック</span><span class="sxs-lookup"><span data-stu-id="32fb5-272">Related topics</span></span>
[<span data-ttu-id="32fb5-273">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-273">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="32fb5-274">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="32fb5-274">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
