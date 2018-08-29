---
title: Skype のビジネス サーバーの 2 要素認証を構成します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '概要: は、Skype のビジネス サーバーの 2 要素認証を構成します。'
ms.openlocfilehash: 4fc8791cd7459ecea89bb8101b2c1a488b6eace2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250802"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="9a138-103">Skype のビジネス サーバーの 2 要素認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="9a138-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="9a138-104">**の概要:** Skype のビジネス サーバーの 2 要素認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="9a138-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="9a138-105">以下のセクションでは、展開に 2 要素認証を構成するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a138-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="9a138-106">二要素認証の詳細については、[オンライン管理者のユーザーの投稿をグリッドの多要素認証を有効にすると Office 365](https://go.microsoft.com/fwlink/p/?LinkId=313332)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a138-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="9a138-107">スマート カード認証をサポートするエンタープライズ ルート証明機関を構成する</span><span class="sxs-lookup"><span data-stu-id="9a138-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="9a138-108">スマート カード認証をサポートするようにエンタープライズ ルート CA を構成する方法を以下の手順で説明します。</span><span class="sxs-lookup"><span data-stu-id="9a138-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="9a138-109">エンタープライズのルート CA をインストールする方法については、[エンタープライズ ルート証明機関をインストール](https://go.microsoft.com/fwlink/p/?LinkID=313364)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a138-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="9a138-110">ドメイン管理者のアカウントを使用してエンタープライズ CA コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="9a138-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="9a138-111">システム マネージャーを起動し、証明機関 Web 登録の役割がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="9a138-112">[**管理ツール**] メニューから**証明機関**管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a138-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="9a138-113">ナビゲーション ウィンドウで、[**証明機関**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="9a138-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="9a138-114">[**証明書テンプレート**] を右クリックし、[**新規作成**] をクリックして、[**発行する証明書テンプレート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a138-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="9a138-115">[**登録エージェント**]、[**スマート カード ユーザー**]、[**スマート カード ログオン**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a138-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="9a138-116">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a138-116">Click **OK**.</span></span>

8. <span data-ttu-id="9a138-117">[**証明書テンプレート**] を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9a138-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="9a138-118">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a138-118">Select **Manage**.</span></span>

10. <span data-ttu-id="9a138-119">スマート カード ユーザー テンプレートのプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a138-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="9a138-120">[**セキュリティ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a138-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="9a138-121">アクセス許可を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="9a138-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="9a138-122">読み取り/登録 (許可) アクセス許可を指定して個別のユーザー AD アカウントを追加します。または</span><span class="sxs-lookup"><span data-stu-id="9a138-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="9a138-123">読み取り/登録 (許可) のアクセス許可を指定してスマート カード ユーザーを含むセキュリティ グループを追加します。または</span><span class="sxs-lookup"><span data-stu-id="9a138-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="9a138-124">読み取り/登録 (許可) のアクセス許可を指定してドメイン ユーザー グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="9a138-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="9a138-125">仮想スマート カード用に Windows 8 を構成する</span><span class="sxs-lookup"><span data-stu-id="9a138-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="9a138-126">2 要素認証とスマート カード テクノロジを展開する場合に考慮する必要がある要素の 1 つは、実装コストです。</span><span class="sxs-lookup"><span data-stu-id="9a138-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="9a138-127">Windows 8 にいくつかの新しいセキュリティ機能が用意されていて、仮想スマート カードのサポートは、最も興味深い新機能の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="9a138-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="9a138-128">バージョン 1.2 仕様を満たす Trusted Platform Module (TPM) チップを搭載したコンピューターでは、ハードウェアの追加費用をかけずにスマート カード ログオンを活用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9a138-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="9a138-129">詳細については、 [Windows 8 での仮想スマート カードの使用](https://go.microsoft.com/fwlink/p/?LinkId=313365)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a138-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="9a138-130">Windows 8 を仮想スマート カード用に構成するには</span><span class="sxs-lookup"><span data-stu-id="9a138-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="9a138-131">ビジネスが有効なユーザーは、Skype の資格情報を使用して Windows 8 のコンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="9a138-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="9a138-132">Windows 8 のスタート画面で、画面の右下隅にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="9a138-133">[**検索**] オプションを選択し、ラー プロンプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="9a138-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="9a138-134">[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a138-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="9a138-135">次のコマンドを実行して、Trusted Platform Module (TPM) 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a138-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```
  Tpm.msc
  ```

6. <span data-ttu-id="9a138-136">TPM 管理コンソールで、TPM 仕様バージョンが 1.2 以上であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a138-137">相互運用性のある Trust Platform Module (TPM) が見つからないことを示すダイアログが表示された場合は、相互運用性のある TPM モジュールがコンピューターにインストールされていること、およびシステム BIOS で有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="9a138-138">TPM 管理コンソールを閉じる</span><span class="sxs-lookup"><span data-stu-id="9a138-138">Close the TPM management console</span></span>

8. <span data-ttu-id="9a138-139">コマンド プロンプトで、次のコマンドを使用して新しい仮想スマート カードを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a138-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="9a138-140">仮想スマート カードを作成するときにカスタム PIN 値を指定するには、代わりに /pin プロンプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a138-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="9a138-141">コマンド プロンプトから、次のコマンドを実行してコンピューター管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a138-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```
  CompMgmt.msc
  ```

10. <span data-ttu-id="9a138-142">コンピューター管理コンソールで、[**デバイス管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a138-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="9a138-143">[**スマート カード リーダー**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="9a138-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="9a138-144">新しい仮想スマート カード リーダーが正しく作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="9a138-145">スマート カード認証にユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="9a138-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="9a138-p104">スマート カードの認証を行うユーザーを登録する方法は、主に 2 つあります。Web 登録を使ってスマート カード認証のユーザーを直接登録する方法がより簡単で、登録エージェントを使う方法はより複雑です。このトピックでは、スマート カードの証明書を自分で登録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a138-p104">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="9a138-149">ユーザーに代わって登録エージェントとしての登録の詳細については、[他のユーザーに代わって証明書の登録](https://go.microsoft.com/fwlink/p/?LinkID=313367)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a138-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="9a138-150">スマート カードの認証を行うユーザーを登録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a138-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="9a138-151">ビジネスが有効なユーザーは、Skype の資格情報を使用して Windows 8 のワークステーションにログインします。</span><span class="sxs-lookup"><span data-stu-id="9a138-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="9a138-152">Internet Explorer を起動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="9a138-153">**証明書機関の Web 登録**ページを参照 (例: https://MyCA.contoso.com/certsrv)。</span><span class="sxs-lookup"><span data-stu-id="9a138-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a138-154">Internet Explorer 10 を使っている場合は、この Web サイトを互換モードで見る必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9a138-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="9a138-155">Web サイトの [**ようこそ**] ページで、[**証明書の要求**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9a138-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="9a138-156">次に、[**証明書の要求の詳細設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9a138-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="9a138-157">[**この CA への要求を作成し送信する。**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9a138-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="9a138-158">[**証明書のテンプレート**] セクションで [**スマート カード ユーザー**] を選び、[証明書の要求の詳細設定] を次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9a138-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="9a138-159">[**キーのオプション**] で次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="9a138-160">[**新しいキー セットを作成する**] ラジオ ボタンを選ぶ</span><span class="sxs-lookup"><span data-stu-id="9a138-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="9a138-161">[**CSP**] で、[**Microsoft ベース スマート カード暗号化プロバイダー**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="9a138-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="9a138-162">[**キー使用法**] で、[**Exchange**] を選ぶ (このオプションのみ有効)</span><span class="sxs-lookup"><span data-stu-id="9a138-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="9a138-163">[**キーのサイズ**] に、2048 と入力する</span><span class="sxs-lookup"><span data-stu-id="9a138-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="9a138-164">[**自動キー コンテナー名**] が選択されている</span><span class="sxs-lookup"><span data-stu-id="9a138-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="9a138-165">その他のボックスはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9a138-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="9a138-166">[**追加オプション**] で次の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="9a138-167">[**要求の形式**] で [**CMC**] を選ぶ。</span><span class="sxs-lookup"><span data-stu-id="9a138-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="9a138-168">[**ハッシュ アルゴリズム**] で [**sha1**] を選ぶ。</span><span class="sxs-lookup"><span data-stu-id="9a138-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="9a138-169">**フレンドリ名**の enterSmardcard 証明書。</span><span class="sxs-lookup"><span data-stu-id="9a138-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="9a138-170">物理カード リーダーを使っている場合は、デバイスにスマート カードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="9a138-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="9a138-171">[**送信**] をクリックして証明書要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="9a138-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="9a138-172">入力を求められたら、仮想スマート カードを作成したときに使った PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a138-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a138-173">既定の仮想スマート カード暗証番号 (pin) の値は、'12345678' です。</span><span class="sxs-lookup"><span data-stu-id="9a138-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="9a138-174">証明書が発行されたら、[**この証明書のインストール**] をクリックして登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="9a138-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="9a138-175">証明書の要求は、「この Web ブラウザーは証明書の要求の生成をサポートしていません」のエラーで失敗すると場合、は、問題を解決するのには 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9a138-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="9a138-176">Active Directory フェデレーション サービス (AD FS 2.0) を構成する</span><span class="sxs-lookup"><span data-stu-id="9a138-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="9a138-177">次のセクションでは、多要素認証をサポートするように Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a138-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="9a138-178">AD FS 2.0 をインストールする方法についてを参照してください[AD FS 2.0 ステップ バイ ステップとガイドにどのように](https://go.microsoft.com/fwlink/p/?LinkId=313374)。</span><span class="sxs-lookup"><span data-stu-id="9a138-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="9a138-179">AD FS 2.0 をインストールするときは、Windows Server Manager を使用して Active Directory フェデレーション サービスの役割を追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="9a138-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="9a138-180">代わりに、ダウンロードして、 [Active Directory フェデレーション サービス 2.0 の RTW のパッケージ](https://go.microsoft.com/fwlink/p/?LinkId=313375)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9a138-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="9a138-181">2 要素認証の AD FS を構成するには</span><span class="sxs-lookup"><span data-stu-id="9a138-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="9a138-182">ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="9a138-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="9a138-183">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="9a138-184">Windows PowerShell コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a138-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="9a138-185">展開に固有のサーバー名を置き換えて以下のコマンドを実行することで、パッシブ認証に対して有効にされる各サーバーとのパートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="9a138-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="9a138-186">[管理ツール] メニューから AD FS 2.0 管理コンソールを起動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="9a138-187">**信頼関係**を展開する > **利用者を信頼**します。</span><span class="sxs-lookup"><span data-stu-id="9a138-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="9a138-188">ビジネス サーバーは、Skype の新しい信頼関係が作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="9a138-189">Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行承認規則を作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9a138-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="9a138-190">Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行変換規則を作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9a138-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="9a138-191">AD FS 2.0 管理コンソールで、証明書利用者の信頼を右クリックし、[**要求規則の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a138-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="9a138-192">[**発行承認規則**] タブをクリックし、新しい承認規則が正しく作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="9a138-193">[**発行変換規則**] タブをクリックし、新しい変換規則が正しく作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="9a138-194">クライアント認証をサポートする AD FS 2.0 の構成</span><span class="sxs-lookup"><span data-stu-id="9a138-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="9a138-195">AD FS 2.0 でスマート カードを使用した認証をサポートできるように構成可能な認証の種類が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="9a138-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="9a138-196">フォーム ベース認証 (FBA)</span><span class="sxs-lookup"><span data-stu-id="9a138-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="9a138-197">トランスポート層セキュリティ クライアント認証</span><span class="sxs-lookup"><span data-stu-id="9a138-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="9a138-198">フォーム ベース認証を使用すると、ユーザー名/パスワードを使用した認証またはスマート カードと PIN を使用した認証をユーザーに許可できる Web ページを開発できます。</span><span class="sxs-lookup"><span data-stu-id="9a138-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="9a138-199">このトピックでは、AD FS 2.0 でトランスポート層セキュリティ クライアント認証を実装する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="9a138-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="9a138-200">AD FS 2.0 の認証の種類の詳細についてを参照してください[AD FS 2.0: ローカルの認証の種類を変更する方法](https://go.microsoft.com/fwlink/p/?LinkId=313384)。</span><span class="sxs-lookup"><span data-stu-id="9a138-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="9a138-201">クライアント認証をサポートするように AD FS 2.0 を構成するには</span><span class="sxs-lookup"><span data-stu-id="9a138-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="9a138-202">ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="9a138-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="9a138-203">エクスプローラーを起動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="9a138-204">C:\inetpub\adfs\ls に移動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="9a138-205">既存の web.config ファイルのバックアップ コピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a138-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="9a138-206">メモ帳を使用して既存の web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a138-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="9a138-207">メニュー バーの [**編集**] をクリックし、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a138-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="9a138-208">検索\<localAuthenticationTypes\>。</span><span class="sxs-lookup"><span data-stu-id="9a138-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="9a138-209">4 つの認証の種類が 1 行に 1 つずつ表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a138-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="9a138-210">TLSClient 認証の種類を含む行をセクションの一覧の一番上に移動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="9a138-211">web.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="9a138-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="9a138-212">管理者特権でコマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="9a138-213">次のコマンドを実行して IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-213">Restart IIS by running the following command:</span></span>

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="9a138-214">Skype for Business Server のパッシブ認証の構成</span><span class="sxs-lookup"><span data-stu-id="9a138-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="9a138-215">次のセクションでは、パッシブ認証をサポートするためにサーバーをビジネス用の Skype を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a138-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="9a138-216">有効になったら、二要素認証は有効になっているユーザーはビジネス クライアント用の Skype を使用してサインインするのには、物理または仮想スマート カードと PIN を有効なを使用する必要になります。</span><span class="sxs-lookup"><span data-stu-id="9a138-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="9a138-p109">レジストラーと Web サービスのパッシブ認証はサービス レベルで有効にすることを強くお勧めします。レジストラーと Web サービスのパッシブ認証をグローバル レベルで有効にすると、サポートされるデスクトップ クライアントでサインインしていないユーザーが組織全体で認証エラーになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a138-p109">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level. If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="9a138-219">Web サービス構成設定</span><span class="sxs-lookup"><span data-stu-id="9a138-219">Web Service Configuration</span></span>

<span data-ttu-id="9a138-220">次の手順では、パッシブ認証を有効にするディレクター、エンタープライズ プール、Standard Edition サーバーにカスタムの Web サービス構成設定を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a138-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="9a138-221">カスタムの Web サービス構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="9a138-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="9a138-222">ビジネス管理者のアカウントは、Skype を使用してビジネス サーバーのフロント エンド サーバーは、Skype にログインします。</span><span class="sxs-lookup"><span data-stu-id="9a138-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="9a138-223">ビジネス サーバー管理シェルには、Skype を起動します。</span><span class="sxs-lookup"><span data-stu-id="9a138-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="9a138-224">ビジネス サーバー管理シェル コマンド ラインの Skype、ディレクター、エンタープライズ プールと Standard Edition サーバーで次のコマンドを実行しているパッシブ認証を有効にするごとに、新しい Web サービス構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="9a138-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="9a138-p110">WsFedPassiveMetadataUri の FQDN の値は、AD FS 2.0 サーバーのフェデレーション サービス名です。フェデレーション サービス名の値は、AD FS 2.0 管理コンソールでナビゲーション ウィンドウの [**サービス**] を右クリックし、[**Edit Federation Service Properties**] を選択すると確認できます。</span><span class="sxs-lookup"><span data-stu-id="9a138-p110">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="9a138-227">次のコマンドを実行して、UseWsFedPassiveAuth と WsFedPassiveMetadataUri の値が正しく設定されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="9a138-228">クライアントでは、パッシブ認証は WebTicket 認証の最も望ましくない方法です。</span><span class="sxs-lookup"><span data-stu-id="9a138-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="9a138-229">すべての取締役、エンタープライズ プール、およびパッシブ認証を有効化する Standard Edition サーバー、他のすべての認証の種類必要があります無効にする Skype のビジネス Web サービスの次のコマンドレットを実行しています。</span><span class="sxs-lookup"><span data-stu-id="9a138-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="9a138-230">次のコマンドレットを実行して、他のすべての認証の種類が無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="9a138-231">プロキシ構成設定</span><span class="sxs-lookup"><span data-stu-id="9a138-231">Proxy Configuration</span></span>

<span data-ttu-id="9a138-232">Skype のビジネス Web サービスの証明書の認証を無効にするとビジネス クライアント用の Skype はレジストラーのサービスへの認証に Kerberos または NTLM などの優先順位の低い認証の種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="9a138-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="9a138-233">Webticket を取得するためにクライアントを許可する証明書の認証が必要、ただし、Kerberos と NTLM 必要があります無効にするレジストラーのサービスです。</span><span class="sxs-lookup"><span data-stu-id="9a138-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="9a138-234">次の手順では、パッシブ認証を有効にするエッジ プール、エンタープライズ プール、Standard Edition サーバーにカスタムのプロキシ構成設定を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a138-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="9a138-235">カスタムのプロキシ構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="9a138-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="9a138-236">ビジネス サーバー管理シェル コマンド ラインの Skype から、次を実行して、パッシブ認証を有効にするビジネス サーバー エッジ プール、エンタープライズ プールと Standard Edition サーバーの各 Skype の新しいプロキシ構成を作成します。コマンド:</span><span class="sxs-lookup"><span data-stu-id="9a138-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="9a138-237">次のコマンドを実行して、他のすべてのプロキシ認証の種類が無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a138-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="9a138-238">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a138-238">See also</span></span>

[<span data-ttu-id="9a138-239">Skype のビジネス サーバーの 2 要素による認証を管理します。</span><span class="sxs-lookup"><span data-stu-id="9a138-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="9a138-240">Business Server のビジネスのクライアントと Skype の Skype で二要素認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="9a138-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use.md)