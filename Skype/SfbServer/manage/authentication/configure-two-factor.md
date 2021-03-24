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
ms.openlocfilehash: 8651be3fbc07bb890637bc8d1c7c99a827d1ea1e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096823"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="70d73-103">Skype for Business Server で 2 要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="70d73-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="70d73-104">**概要:** Skype for Business Server で 2 要素認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="70d73-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="70d73-105">以下のセクションでは、展開の 2 要素認証を構成するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d73-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="70d73-106">2 要素認証の詳細については、「オンライン管理者Office [365](https://go.microsoft.com/fwlink/p/?LinkId=313332)多要素認証の有効化 - Grid User Post 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d73-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="70d73-107">スマート カード認証をサポートするためのエンタープライズ ルート証明機関の構成</span><span class="sxs-lookup"><span data-stu-id="70d73-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="70d73-108">次の手順では、スマート カード認証をサポートするためにエンタープライズ ルート CA を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d73-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="70d73-109">エンタープライズ ルート CA をインストールする方法の詳細については、「エンタープライズ ルート証明機関 [のインストール」を参照してください](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10))。</span><span class="sxs-lookup"><span data-stu-id="70d73-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).</span></span>

1. <span data-ttu-id="70d73-110">ドメイン管理者アカウントを使用してエンタープライズ CA コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="70d73-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="70d73-111">System Manager を起動し、証明機関 Web 登録の役割がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="70d73-112">[管理 **ツール] メニュー** から、証明機関の **管理コンソールを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="70d73-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="70d73-113">[ナビゲーション] ウィンドウで、[証明機関] **を展開します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="70d73-114">[証明書テンプレート]**を右クリックし、[\*\*\*\*新規]** を選択し、[**発行する証明書テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="70d73-115">[ **登録エージェント]** **、[Smartcard ユーザー] 、** および **[スマートカード ログオン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="70d73-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70d73-116">Click **OK**.</span></span>

8. <span data-ttu-id="70d73-117">[証明書テンプレート] **を右クリックします**。</span><span class="sxs-lookup"><span data-stu-id="70d73-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="70d73-118">[管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-118">Select **Manage**.</span></span>

10. <span data-ttu-id="70d73-119">Smartcard ユーザー テンプレートのプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="70d73-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="70d73-120">[セキュリティ] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="70d73-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="70d73-121">アクセス許可を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="70d73-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="70d73-122">読み取り/登録ADアクセス許可を持つ個々のユーザー アカウントを追加するか、または</span><span class="sxs-lookup"><span data-stu-id="70d73-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="70d73-123">読み取り/登録 (許可) アクセス許可を持つスマート カード ユーザーを含むセキュリティ グループを追加する、または</span><span class="sxs-lookup"><span data-stu-id="70d73-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="70d73-124">読み取り/登録 (許可) アクセス許可を持つドメイン ユーザー グループを追加する</span><span class="sxs-lookup"><span data-stu-id="70d73-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="70d73-125">仮想Windows 8カードの構成</span><span class="sxs-lookup"><span data-stu-id="70d73-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="70d73-126">2 要素認証とスマート カード テクノロジを展開する際に考慮すべき 1 つの要素は、実装のコストです。</span><span class="sxs-lookup"><span data-stu-id="70d73-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="70d73-127">Windows 8新しいセキュリティ機能の数を提供し、最も興味深い新機能の 1 つは仮想スマート カードのサポートです。</span><span class="sxs-lookup"><span data-stu-id="70d73-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="70d73-128">仕様バージョン 1.2 を満たすトラステッド プラットフォーム モジュール (TPM) チップを搭載したコンピューターの場合、組織はハードウェアに追加の投資をすることなく、スマート カード ログオンの利点を得る事が可能になります。</span><span class="sxs-lookup"><span data-stu-id="70d73-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="70d73-129">詳細については、「Using Virtual Smart Cards with [Windows 8」 を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=313365)。</span><span class="sxs-lookup"><span data-stu-id="70d73-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="70d73-130">仮想スマート カードWindows 8を構成するには</span><span class="sxs-lookup"><span data-stu-id="70d73-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="70d73-131">Skype for Business が有効なWindows 8資格情報を使用して、コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="70d73-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="70d73-132">[スタートWindows 8画面で、画面の右下隅にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="70d73-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="70d73-133">[検索] **オプションを** 選択し、[コマンド プロンプト] を検索します。</span><span class="sxs-lookup"><span data-stu-id="70d73-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="70d73-134">[コマンド プロンプト] **を右クリックし**、[管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="70d73-135">次のコマンドを実行して、信頼できるプラットフォーム モジュール (TPM) 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="70d73-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="70d73-136">TPM 管理コンソールで、TPM 仕様のバージョンが 1.2 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d73-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="70d73-137">互換性のある信頼プラットフォーム モジュール (TPM) が見つからないことを示すダイアログが表示される場合は、コンピューターに互換性のある TPM モジュールがあり、システム BIOS で有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="70d73-138">TPM 管理コンソールを閉じる</span><span class="sxs-lookup"><span data-stu-id="70d73-138">Close the TPM management console</span></span>

8. <span data-ttu-id="70d73-139">コマンド プロンプトから、次のコマンドを使用して新しい仮想スマート カードを作成します。</span><span class="sxs-lookup"><span data-stu-id="70d73-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="70d73-140">仮想スマート カードの作成時にカスタム PIN 値を指定するには、代わりに /pin プロンプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="70d73-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="70d73-141">コマンド プロンプトから、次のコマンドを実行してコンピューター管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="70d73-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="70d73-142">[コンピューターの管理] コンソールで、[デバイスの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="70d73-143">[ **スマート カード リーダー] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="70d73-144">新しい仮想スマート カード リーダーが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="70d73-145">スマート カード認証用にユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="70d73-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="70d73-146">スマート カード認証用にユーザーを登録するには、通常 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="70d73-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="70d73-147">簡単な方法では、ユーザーが Web 登録を使用してスマート カード認証に直接登録する方法と、登録エージェントを使用する方法が複雑になります。</span><span class="sxs-lookup"><span data-stu-id="70d73-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="70d73-148">このトピックでは、スマートカード証明書の自己登録について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d73-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="70d73-149">登録エージェントとしてユーザーに代わって登録する方法の詳細については、「他のユーザーに代わって証明書を登録する」 [を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="70d73-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="70d73-150">スマート カード認証のユーザーを登録するには</span><span class="sxs-lookup"><span data-stu-id="70d73-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="70d73-151">Skype for Business が有効なWindows 8資格情報を使用して、クライアント ワークステーションにログインします。</span><span class="sxs-lookup"><span data-stu-id="70d73-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="70d73-152">起動Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="70d73-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="70d73-153">[証明機関 Web **登録] ページを参照** します (例 https://MyCA.contoso.com/certsrv) : .</span><span class="sxs-lookup"><span data-stu-id="70d73-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="70d73-154">10 から 10 Internet Explorer使用している場合は、この Web サイトを互換モードで表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d73-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="70d73-155">[ようこそ] **ページで** 、[証明書の **要求] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="70d73-156">次に、[高度な **要求] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="70d73-157">[この **CA に要求を作成して送信する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="70d73-158">[ **証明書テンプレート] セクションで [Smartcard User]** **を** 選択し、次の値で高度な証明書要求を完了します。</span><span class="sxs-lookup"><span data-stu-id="70d73-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="70d73-159">**キー オプションは、** 次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="70d73-160">[新しい **キー セットの作成] ラジオ ボタンを** 選択する</span><span class="sxs-lookup"><span data-stu-id="70d73-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="70d73-161">**CSP の場合** は **、[Microsoft Base Smart Card Crypto Provider] (Microsoft Base Smart Card Crypto Provider) を選択します。**</span><span class="sxs-lookup"><span data-stu-id="70d73-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="70d73-162">[ **キーの使用法]** で **、[Exchange]** を選択します (使用可能な唯一のオプションです)。</span><span class="sxs-lookup"><span data-stu-id="70d73-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="70d73-163">[ **キー のサイズ]** に「2048」と入力します。</span><span class="sxs-lookup"><span data-stu-id="70d73-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="70d73-164">[自動キー **コンテナー名] が選択** されているのを確認する</span><span class="sxs-lookup"><span data-stu-id="70d73-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="70d73-165">他のボックスはオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="70d73-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="70d73-166">[追加 **オプション] で** 、次の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="70d73-167">[要求 **形式] で\*\*\*\*[CMC] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="70d73-168">[ハッシュ **アルゴリズム] で** **[sha1] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="70d73-169">[ **フレンドリー名] に** 「Smardcard Certificate」と入力します。</span><span class="sxs-lookup"><span data-stu-id="70d73-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="70d73-170">物理スマートカード リーダーを使用している場合は、スマート カードをデバイスに挿入します。</span><span class="sxs-lookup"><span data-stu-id="70d73-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="70d73-171">[送信 **] を** クリックして証明書要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="70d73-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="70d73-172">メッセージが表示されたら、仮想スマート カードの作成に使用した PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="70d73-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70d73-173">既定の仮想スマート カードの PIN 値は '12345678' です。</span><span class="sxs-lookup"><span data-stu-id="70d73-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="70d73-174">証明書が発行された後、[この証明書のインストール] **を** クリックして登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="70d73-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="70d73-175">"この Web ブラウザーは証明書要求の生成をサポートしません" というエラーで証明書要求が失敗した場合、次の 3 つの方法で問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="70d73-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="70d73-176">Active Directory フェデレーション サービスの構成 (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="70d73-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="70d73-177">次のセクションでは、多要素認証をサポートするために Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d73-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="70d73-178">FS 2.0 をADする方法については [、「AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))のステップ バイ ステップ」および「How To Guides」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d73-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>

> [!NOTE]
> <span data-ttu-id="70d73-179">FS 2.0 ADインストールする場合は、Windows Server Manager を使用して Active Directory フェデレーション サービスの役割を追加しません。</span><span class="sxs-lookup"><span data-stu-id="70d73-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="70d73-180">代わりに、Active Directory フェデレーション サービス [2.0 RTW パッケージをダウンロードしてインストールします](https://go.microsoft.com/fwlink/p/?LinkId=313375)。</span><span class="sxs-lookup"><span data-stu-id="70d73-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="70d73-181">2 要素認証AD FS を構成するには</span><span class="sxs-lookup"><span data-stu-id="70d73-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="70d73-182">ドメイン管理者アカウントをAD FS 2.0 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="70d73-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="70d73-183">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="70d73-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="70d73-184">コマンド ラインWindows PowerShell、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70d73-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="70d73-185">次のコマンドを実行して、展開に固有のサーバー名を置き換え、パッシブ認証を有効にする各サーバーとのパートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="70d73-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="70d73-186">[管理ツール] メニューから、FS 2.0 ADを起動します。</span><span class="sxs-lookup"><span data-stu-id="70d73-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="70d73-187">[**信頼関係証明書利用者**  >  **の信頼] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="70d73-188">Skype for Business Server に対して新しい信頼が作成されたと確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="70d73-189">次のコマンドを実行して、証明書利用者信頼の発行承認ルールを作成Windows PowerShell使用します。</span><span class="sxs-lookup"><span data-stu-id="70d73-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="70d73-190">次のコマンドを実行して、証明書利用者信頼の発行変換ルールを作成Windows PowerShell使用します。</span><span class="sxs-lookup"><span data-stu-id="70d73-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="70d73-191">FS 2.0 ADから、証明書利用者の信頼を右クリックし、[クレーム ルールの編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="70d73-192">[発行 **承認ルール] タブを** 選択し、新しい承認ルールが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="70d73-193">[発行 **変換ルール] タブを** 選択し、新しい変換ルールが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="70d73-194">クライアント認証AD FS 2.0 の構成</span><span class="sxs-lookup"><span data-stu-id="70d73-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="70d73-195">FS 2.0 でスマート カードを使用した認証をサポートAD、次の 2 種類の認証を構成できます。</span><span class="sxs-lookup"><span data-stu-id="70d73-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="70d73-196">フォーム ベース認証 (FBA)</span><span class="sxs-lookup"><span data-stu-id="70d73-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="70d73-197">トランスポート層セキュリティ クライアント認証</span><span class="sxs-lookup"><span data-stu-id="70d73-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="70d73-198">フォーム ベース認証を使用すると、ユーザーがユーザー名/パスワードを使用するか、スマート カードと PIN を使用して認証できる Web ページを開発できます。</span><span class="sxs-lookup"><span data-stu-id="70d73-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="70d73-199">このトピックでは、FS 2.0 を使用してトランスポート層セキュリティ クライアント認証を実装するADを説明します。</span><span class="sxs-lookup"><span data-stu-id="70d73-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="70d73-200">FS 2.0 認証ADの詳細については [、「AD FS 2.0: ローカル](https://go.microsoft.com/fwlink/p/?LinkId=313384)認証の種類を変更する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d73-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="70d73-201">クライアント認証AD FS 2.0 を構成するには</span><span class="sxs-lookup"><span data-stu-id="70d73-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="70d73-202">ドメイン管理者アカウントをAD FS 2.0 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="70d73-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="70d73-203">Windows エクスプローラーを起動します。</span><span class="sxs-lookup"><span data-stu-id="70d73-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="70d73-204">C:\inetpub\adfs\ls への参照</span><span class="sxs-lookup"><span data-stu-id="70d73-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="70d73-205">既存のファイルのバックアップ コピーをweb.configします。</span><span class="sxs-lookup"><span data-stu-id="70d73-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="70d73-206">メモ帳を使用してweb.configファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="70d73-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="70d73-207">メニュー バーで [編集] を選択 **し** 、[検索] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="70d73-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="70d73-208">を検索します \<localAuthenticationTypes\> 。</span><span class="sxs-lookup"><span data-stu-id="70d73-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="70d73-209">一覧には、1 行に 1 つの 4 つの認証の種類があります。</span><span class="sxs-lookup"><span data-stu-id="70d73-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="70d73-210">TLSClient 認証の種類を含む行をセクションの一覧の一番上に移動します。</span><span class="sxs-lookup"><span data-stu-id="70d73-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="70d73-211">ファイルを保存して閉web.configします。</span><span class="sxs-lookup"><span data-stu-id="70d73-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="70d73-212">管理者特権でコマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="70d73-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="70d73-213">次のコマンドを実行して IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="70d73-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="70d73-214">Skype for Business Server パッシブ認証の構成</span><span class="sxs-lookup"><span data-stu-id="70d73-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="70d73-215">次のセクションでは、パッシブ認証をサポートするために Skype for Business Server を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d73-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="70d73-216">有効にすると、2 要素認証が有効になっているユーザーは、物理スマート カードまたは仮想スマート カードと有効な PIN を使用して Skype for Business クライアントを使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d73-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="70d73-217">レジストラーと Web サービスのパッシブ認証をサービス レベルで有効に強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="70d73-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="70d73-218">レジストラーと Web サービスでグローバル レベルでパッシブ認証が有効になっている場合、サポートされているデスクトップ クライアントでサインインしていないユーザーの組織全体の認証エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70d73-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="70d73-219">Web サービスの構成</span><span class="sxs-lookup"><span data-stu-id="70d73-219">Web Service Configuration</span></span>

<span data-ttu-id="70d73-220">次の手順では、パッシブ認証を有効にするディレクター、エンタープライズ プール、および Standard Edition サーバー用のカスタム Web サービス構成を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d73-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="70d73-221">カスタム Web サービス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="70d73-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="70d73-222">Skype for Business 管理者アカウントを使用して Skype for Business Server フロントエンド サーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="70d73-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="70d73-223">Skype for Business Server 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="70d73-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="70d73-224">Skype for Business Server Management Shell コマンド ラインから、次のコマンドを実行してパッシブ認証を有効にするディレクター、エンタープライズ プール、および Standard Edition サーバーごとに新しい Web サービス構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="70d73-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="70d73-225">WsFedPassiveMetadataUri FQDN の値は、FS 2.0 サーバーのADサービス名です。</span><span class="sxs-lookup"><span data-stu-id="70d73-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="70d73-226">フェデレーション サービス名の値は、AD FS 2.0 管理コンソールのナビゲーション ウィンドウで [サービス] を右クリックし、[フェデレーション サービスのプロパティの編集] を選択することで **確認できます**。</span><span class="sxs-lookup"><span data-stu-id="70d73-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="70d73-227">次のコマンドを実行して、UseWsFedPassiveAuth および WsFedPassiveMetadataUri の値が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="70d73-228">クライアントの場合、パッシブ認証は Web チケット認証の最も優先される認証方法です。</span><span class="sxs-lookup"><span data-stu-id="70d73-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="70d73-229">パッシブ認証が有効になるすべてのディレクター、エンタープライズ プール、および Standard Edition サーバーでは、次のコマンドレットを実行して、Skype for Business Web Services で他のすべての認証の種類を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d73-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="70d73-230">次のコマンドレットを実行して、他のすべての認証の種類が正常に無効にされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="70d73-231">プロキシ構成</span><span class="sxs-lookup"><span data-stu-id="70d73-231">Proxy Configuration</span></span>

<span data-ttu-id="70d73-232">Skype for Business Web Services で証明書認証が無効になっている場合、Skype for Business クライアントは、レジストラー サービスに対する認証に、Kerberos や NTLM などのあまり優先されない認証の種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="70d73-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="70d73-233">クライアントが Web チケットを取得するには、証明書認証が必要ですが、レジストラー サービスでは Kerberos と NTLM を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d73-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="70d73-234">次の手順では、パッシブ認証を有効にするエッジ プール、エンタープライズ プール、および Standard Edition サーバー用のカスタム プロキシ構成を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d73-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="70d73-235">カスタム プロキシ構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="70d73-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="70d73-236">Skype for Business Server Management Shell コマンド ラインから、次のコマンドを実行してパッシブ認証を有効にする Skype for Business Server エッジ プール、エンタープライズ プール、および Standard Edition サーバーごとに新しいプロキシ構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="70d73-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="70d73-237">次のコマンドを実行して、他のすべてのプロキシ認証の種類が正常に無効にされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="70d73-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="70d73-238">関連項目</span><span class="sxs-lookup"><span data-stu-id="70d73-238">See also</span></span>

[<span data-ttu-id="70d73-239">Skype for Business Server での 2 要素認証の管理</span><span class="sxs-lookup"><span data-stu-id="70d73-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="70d73-240">Skype for Business クライアントと Skype for Business Server で 2 要素認証を使用する</span><span class="sxs-lookup"><span data-stu-id="70d73-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)