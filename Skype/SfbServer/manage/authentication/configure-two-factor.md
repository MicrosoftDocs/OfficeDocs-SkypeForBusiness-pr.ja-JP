---
title: Skype for Business Server で 2 要素認証を構成する
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
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '概要: Skype for Business Server で 2 要素認証を構成します。'
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814417"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="42aa4-103">Skype for Business Server で 2 要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="42aa4-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="42aa4-104">**概要:** Skype for Business Server で 2 要素認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="42aa4-105">以下のセクションでは、展開用に 2 要素認証を構成するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="42aa4-106">2 要素認証の詳細については [、「Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42aa4-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="42aa4-107">スマート カード認証をサポートするためのエンタープライズ ルート証明機関の構成</span><span class="sxs-lookup"><span data-stu-id="42aa4-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="42aa4-108">次の手順では、スマート カード認証をサポートするためにエンタープライズ ルート CA を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="42aa4-109">エンタープライズ ルート CA をインストールする方法については、「エンタープライズ ルート証明機関のインストール」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=313364)。</span><span class="sxs-lookup"><span data-stu-id="42aa4-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="42aa4-110">ドメイン管理者アカウントを使用してエンタープライズ CA コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="42aa4-111">システム マネージャーを起動し、証明機関 Web 登録の役割がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="42aa4-112">[管理 **ツール] メニュー** から証明機関管理コンソール **を** 開きます。</span><span class="sxs-lookup"><span data-stu-id="42aa4-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="42aa4-113">ナビゲーション ウィンドウで、[証明機関] **を展開します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="42aa4-114">[証明書テンプレート] **を右クリックし、[** 新規] **を選択** し、[発行する **証明書テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="42aa4-115">登録 **エージェント、スマート\*\*\*\*カード ユーザー、および\*\*\*\*スマート カード ログオンを選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="42aa4-116">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-116">Click **OK**.</span></span>

8. <span data-ttu-id="42aa4-117">[証明書テンプレート] **を右クリックします**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="42aa4-118">[管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-118">Select **Manage**.</span></span>

10. <span data-ttu-id="42aa4-119">Smartcard ユーザー テンプレートのプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="42aa4-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="42aa4-120">[セキュリティ] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="42aa4-121">アクセス許可を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="42aa4-122">読み取り/AD (許可) アクセス許可を持つ個々のユーザー アカウントを追加する、または</span><span class="sxs-lookup"><span data-stu-id="42aa4-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="42aa4-123">読み取り/登録 (許可) アクセス許可を持つスマート カード ユーザーを含むセキュリティ グループを追加する、または</span><span class="sxs-lookup"><span data-stu-id="42aa4-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="42aa4-124">読み取り/登録 (許可) アクセス許可を持つ Domain Users グループを追加する</span><span class="sxs-lookup"><span data-stu-id="42aa4-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="42aa4-125">仮想Windows 8カードの構成</span><span class="sxs-lookup"><span data-stu-id="42aa4-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="42aa4-126">2 要素認証とスマート カード テクノロジを展開する際に考慮する必要がある要素の 1 つは、実装のコストです。</span><span class="sxs-lookup"><span data-stu-id="42aa4-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="42aa4-127">Windows 8には多くの新しいセキュリティ機能が用意されています。最も興味深い新機能の 1 つは仮想スマート カードのサポートです。</span><span class="sxs-lookup"><span data-stu-id="42aa4-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="42aa4-128">仕様バージョン 1.2 を満たすトラステッド プラットフォーム モジュール (TPM) チップを搭載したコンピューターでは、ハードウェアに追加の投資を行わずにスマート カード ログオンのメリットを得る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42aa4-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="42aa4-129">詳細については、「仮想スマート カード[と仮想スマート カードの使用」をWindows 8。](https://go.microsoft.com/fwlink/p/?LinkId=313365)</span><span class="sxs-lookup"><span data-stu-id="42aa4-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="42aa4-130">仮想スマート カードWindows 8を構成するには</span><span class="sxs-lookup"><span data-stu-id="42aa4-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="42aa4-131">Skype for Business が有効Windows 8の資格情報を使用して、ユーザーのコンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="42aa4-132">スタートWindows 8画面で、画面の右下隅にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="42aa4-133">[検索 **] オプション** を選択し、コマンド プロンプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="42aa4-134">コマンド プロンプトを右 **クリックし、[** 管理者として実行 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="42aa4-135">次のコマンドを実行して、トラステッド プラットフォーム モジュール (TPM) 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="42aa4-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="42aa4-136">TPM 管理コンソールから、TPM 仕様のバージョンが 1.2 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42aa4-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="42aa4-137">互換性信頼プラットフォーム モジュール (TPM) が見つからないことを示すダイアログが表示された場合は、コンピューターに互換性のある TPM モジュールがあり、システム BIOS で有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="42aa4-138">TPM 管理コンソールを閉じる</span><span class="sxs-lookup"><span data-stu-id="42aa4-138">Close the TPM management console</span></span>

8. <span data-ttu-id="42aa4-139">コマンド プロンプトで、次のコマンドを使用して新しい仮想スマート カードを作成します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="42aa4-140">仮想スマート カードの作成時にカスタム PIN 値を指定するには、代わりに /pin プロンプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="42aa4-141">コマンド プロンプトで、次のコマンドを実行して、コンピューターの管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="42aa4-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="42aa4-142">コンピューターの管理コンソールで、[デバイス管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="42aa4-143">[スマート **カード リーダー] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="42aa4-144">新しい仮想スマート カード リーダーが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="42aa4-145">スマート カード認証用にユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="42aa4-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="42aa4-146">スマート カード認証用にユーザーを登録するには、通常 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="42aa4-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="42aa4-147">より簡単な方法では、ユーザーが Web 登録を使用してスマート カード認証に直接登録する方法と、登録エージェントを使用する方法が複雑になります。</span><span class="sxs-lookup"><span data-stu-id="42aa4-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="42aa4-148">このトピックでは、スマートカード証明書の自己登録について説明します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="42aa4-149">登録エージェントとしてユーザーの代わりに登録する方法の詳細については、「他のユーザーの代わりに証明書を登録する」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=313367)。</span><span class="sxs-lookup"><span data-stu-id="42aa4-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="42aa4-150">スマート カード認証用にユーザーを登録するには</span><span class="sxs-lookup"><span data-stu-id="42aa4-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="42aa4-151">Skype for Business が有効Windows 8の資格情報を使用して、Windows 8 ワークステーションにログインします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="42aa4-152">起動Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="42aa4-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="42aa4-153">証明機関 Web **登録ページ** (例: https://MyCA.contoso.com/certsrv) .</span><span class="sxs-lookup"><span data-stu-id="42aa4-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="42aa4-154">Internet Explorer 10 を使用している場合は、この Web サイトを互換モードで表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42aa4-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="42aa4-155">[ようこそ] **ページで** 、[証明書の要求 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="42aa4-156">次に、[詳細な要求 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="42aa4-157">[作成 **] を選択し、この CA に要求を送信します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="42aa4-158">[ **証明書テンプレート] セクションで** **[Smartcard** ユーザー] を選択し、次の値で証明書の詳細要求を完了します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="42aa4-159">**キー オプションは、** 次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="42aa4-160">[新しい **キー セットの作成] ラジオ ボタンを** 選択する</span><span class="sxs-lookup"><span data-stu-id="42aa4-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="42aa4-161">**CSP の場合** は **、Microsoft Base スマート カード暗号化プロバイダーを選択します。**</span><span class="sxs-lookup"><span data-stu-id="42aa4-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="42aa4-162">キー **使用法の場合は\*\*\*\*、[Exchange]** を選択します (これが唯一のオプションです)。</span><span class="sxs-lookup"><span data-stu-id="42aa4-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="42aa4-163">キー **サイズの場合は**、「2048」と入力します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="42aa4-164">[自動キー **コンテナー名] が選択** されているのを確認する</span><span class="sxs-lookup"><span data-stu-id="42aa4-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="42aa4-165">他のボックスはオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="42aa4-166">[その **他のオプション] で** 、次の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="42aa4-167">要求 **形式の場合は\*\*\*\*、CMC を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="42aa4-168">ハッシュ **アルゴリズムの場合は\*\*\*\*、sha1 を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="42aa4-169">[Friendly **Name]** に「Smardcard Certificate」と入力します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="42aa4-170">物理スマートカード リーダーを使用している場合は、スマート カードをデバイスに挿入します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="42aa4-171">[送信 **] を** クリックして証明書要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="42aa4-172">メッセージが表示されたら、仮想スマート カードの作成に使用した PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="42aa4-173">既定の仮想スマート カード PIN 値は '12345678' です。</span><span class="sxs-lookup"><span data-stu-id="42aa4-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="42aa4-174">証明書が発行された後、[この証明書のインストール] をクリックして登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="42aa4-175">「この Web ブラウザーは証明書要求の生成をサポートしません」というエラーで証明書要求が失敗した場合、次の 3 つの方法で問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="42aa4-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="42aa4-176">Active Directory フェデレーション サービスを構成する (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="42aa4-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="42aa4-177">次のセクションでは、多要素認証をサポートするために Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="42aa4-178">AD FS 2.0 のインストール方法については、「AD [FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42aa4-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="42aa4-179">FS 2.0 ADインストールする場合は、Windows Server Manager を使用して Active Directory フェデレーション サービスの役割を追加しません。</span><span class="sxs-lookup"><span data-stu-id="42aa4-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="42aa4-180">代わりに、Active Directory フェデレーション サービス [2.0 RTW パッケージをダウンロードしてインストールします](https://go.microsoft.com/fwlink/p/?LinkId=313375)。</span><span class="sxs-lookup"><span data-stu-id="42aa4-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="42aa4-181">2 要素認証AD FS を構成するには</span><span class="sxs-lookup"><span data-stu-id="42aa4-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="42aa4-182">ドメイン管理者アカウントをAD FS 2.0 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="42aa4-183">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="42aa4-184">コマンド ラインWindows PowerShell次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="42aa4-185">次のコマンドを実行して、展開に固有のサーバー名を置き換え、パッシブ認証が有効になる各サーバーとのパートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="42aa4-186">[管理ツール] メニューから、AD FS 2.0 管理コンソールを起動します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="42aa4-187">[**信頼関係証明書利用者**  >  **信頼] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="42aa4-188">Skype for Business Server に対して新しい信頼が作成されたのを確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="42aa4-189">次のコマンドを実行して、証明書利用者信頼の発行承認Windows PowerShellを作成して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="42aa4-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="42aa4-190">次のコマンドを実行して、証明書利用者信頼の発行変換Windows PowerShell作成して割り当てる。</span><span class="sxs-lookup"><span data-stu-id="42aa4-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="42aa4-191">AD FS 2.0 管理コンソールで、証明書利用者信頼を右クリックし、[要求規則の編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="42aa4-192">[発行 **承認規則]** タブを選択し、新しい承認ルールが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="42aa4-193">[発行 **変換ルール]** タブを選択し、新しい変換ルールが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="42aa4-194">クライアント認証ADサポートするための FS 2.0 の構成</span><span class="sxs-lookup"><span data-stu-id="42aa4-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="42aa4-195">FS 2.0 でスマート カードを使用した認証をサポートAD、次の 2 種類の認証を構成できます。</span><span class="sxs-lookup"><span data-stu-id="42aa4-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="42aa4-196">フォーム ベース認証 (FBA)</span><span class="sxs-lookup"><span data-stu-id="42aa4-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="42aa4-197">トランスポート層セキュリティ クライアント認証</span><span class="sxs-lookup"><span data-stu-id="42aa4-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="42aa4-198">フォーム ベース認証を使用すると、ユーザー名/パスワードを使用するか、スマート カードと PIN を使用してユーザーを認証できる Web ページを開発できます。</span><span class="sxs-lookup"><span data-stu-id="42aa4-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="42aa4-199">このトピックでは、FS 2.0 でトランスポート層セキュリティ クライアント認証を実装するADについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="42aa4-200">FS 2.0 認証のAD詳細については、「AD FS [2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="42aa4-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="42aa4-201">クライアント認証AD FS 2.0 を構成するには</span><span class="sxs-lookup"><span data-stu-id="42aa4-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="42aa4-202">ドメイン管理者アカウントをAD FS 2.0 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="42aa4-203">Windows エクスプローラーを起動します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="42aa4-204">C:\inetpub\adfs\ls に移動します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="42aa4-205">既存のファイルのバックアップ コピーをweb.configします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="42aa4-206">メモ帳を使用してweb.configファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="42aa4-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="42aa4-207">メニュー バーから [編集] **を選択し** 、[検索] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="42aa4-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="42aa4-208">を検索します \<localAuthenticationTypes\> 。</span><span class="sxs-lookup"><span data-stu-id="42aa4-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="42aa4-209">4 種類の認証が 1 行に 1 つ表示されます。</span><span class="sxs-lookup"><span data-stu-id="42aa4-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="42aa4-210">TLSClient 認証の種類を含む行を、セクションの一覧の一番上に移動します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="42aa4-211">ファイルを保存して閉web.configします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="42aa4-212">管理者特権でコマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="42aa4-213">次のコマンドを実行して IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="42aa4-214">Skype for Business Server パッシブ認証の構成</span><span class="sxs-lookup"><span data-stu-id="42aa4-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="42aa4-215">次のセクションでは、パッシブ認証をサポートするために Skype for Business Server を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="42aa4-216">有効にすると、2 要素認証が有効になっているユーザーは、物理スマート カードまたは仮想スマート カードと有効な PIN を使用して Skype for Business クライアントを使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42aa4-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="42aa4-217">お客様は、サービス レベルでレジストラーと Web サービスのパッシブ認証を有効に強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="42aa4-218">レジストラーと Web サービスでパッシブ認証がグローバル レベルで有効になっている場合、サポートされているデスクトップ クライアントでサインインしていないユーザーに対して組織全体の認証エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42aa4-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="42aa4-219">Web サービスの構成</span><span class="sxs-lookup"><span data-stu-id="42aa4-219">Web Service Configuration</span></span>

<span data-ttu-id="42aa4-220">以下の手順では、パッシブ認証を有効にするディレクター、エンタープライズ プール、および Standard Edition サーバー用のカスタム Web サービス構成を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="42aa4-221">カスタム Web サービス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="42aa4-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="42aa4-222">Skype for Business 管理者アカウントを使用して、Skype for Business Server フロントエンド サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="42aa4-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="42aa4-223">Skype for Business Server 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="42aa4-224">Skype for Business Server 管理シェル コマンドラインから、次のコマンドを実行してパッシブ認証を有効にするディレクター、エンタープライズ プール、および Standard Edition サーバーごとに新しい Web サービス構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="42aa4-225">WsFedPassiveMetadataUri FQDN の値は、AD FS 2.0 サーバーのフェデレーション サービス名です。</span><span class="sxs-lookup"><span data-stu-id="42aa4-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="42aa4-226">フェデレーション サービス名の値は、ナビゲーション ウィンドウから [サービス] を右クリックし、[フェデレーション サービスのプロパティの編集] を選択すると、AD FS 2.0 管理コンソール **にあります。**</span><span class="sxs-lookup"><span data-stu-id="42aa4-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="42aa4-227">次のコマンドを実行して、UseWsFedPassiveAuth と WsFedPassiveMetadataUri の値が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="42aa4-228">クライアントの場合、パッシブ認証は Webticket 認証の最も優先される認証方法です。</span><span class="sxs-lookup"><span data-stu-id="42aa4-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="42aa4-229">パッシブ認証が有効になるすべてのディレクター、エンタープライズ プール、および Standard Edition サーバーでは、次のコマンドレットを実行して、Skype for Business Web サービスで他のすべての種類の認証を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42aa4-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="42aa4-230">次のコマンドレットを実行して、他のすべての認証の種類が正常に無効にされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="42aa4-231">プロキシ構成</span><span class="sxs-lookup"><span data-stu-id="42aa4-231">Proxy Configuration</span></span>

<span data-ttu-id="42aa4-232">Skype for Business Web サービスに対して証明書認証が無効になっている場合、Skype for Business クライアントは、Kerberos や NTLM などの優先されない認証の種類を使用してレジストラー サービスへの認証を行います。</span><span class="sxs-lookup"><span data-stu-id="42aa4-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="42aa4-233">ただし、クライアントが Webticket を取得するには証明書認証が必要ですが、レジストラー サービスに対して Kerberos と NTLM を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42aa4-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="42aa4-234">次の手順では、パッシブ認証が有効になるエッジ プール、エンタープライズ プール、および Standard Edition サーバー用のカスタム プロキシ構成を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="42aa4-235">カスタム プロキシ構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="42aa4-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="42aa4-236">Skype for Business Server 管理シェル コマンドラインから、次のコマンドを実行してパッシブ認証を有効にする Skype for Business Server エッジ プール、エンタープライズ プール、および Standard Edition サーバーごとに新しいプロキシ構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="42aa4-237">次のコマンドを実行して、他のすべてのプロキシ認証の種類が正常に無効にされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="42aa4-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="42aa4-238">関連項目</span><span class="sxs-lookup"><span data-stu-id="42aa4-238">See also</span></span>

[<span data-ttu-id="42aa4-239">Skype for Business Server で 2 要素認証を管理する</span><span class="sxs-lookup"><span data-stu-id="42aa4-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="42aa4-240">Skype for Business クライアントと Skype for Business Server で 2 要素認証を使用する</span><span class="sxs-lookup"><span data-stu-id="42aa4-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)
