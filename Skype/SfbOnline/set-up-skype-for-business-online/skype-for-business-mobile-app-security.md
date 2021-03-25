---
title: Skype for Business のモバイル アプリのセキュリティ
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'ユーザー向けモバイル アプリのセキュリティを設定する方法について学習します。 '
ms.openlocfilehash: d599542970cec5aa4206f29d3ff7fa27ce36e9a0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109953"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="afef2-103">Skype for Business のモバイル アプリのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="afef2-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="afef2-104">Skype for Business クライアントのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="afef2-104">Skype for Business Client Security</span></span>

<span data-ttu-id="afef2-105">この記事では、Skype for Business モバイル アプリのデータ暗号化に関する情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="afef2-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="afef2-106">**ユーザー名/パスワード**</span><span class="sxs-lookup"><span data-stu-id="afef2-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="afef2-107">**アプリ データ (会話、 <br/> 連絡先リスト、会議)**</span><span class="sxs-lookup"><span data-stu-id="afef2-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="afef2-108">**診断ログ**</span><span class="sxs-lookup"><span data-stu-id="afef2-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="afef2-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="afef2-109">**Android**</span></span> <br/> |<span data-ttu-id="afef2-110">Android アカウントには資格情報情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="afef2-110">We store credentials information in Android Accounts.</span></span> <span data-ttu-id="afef2-111">アカウントに保存する前に資格情報も暗号化します。</span><span class="sxs-lookup"><span data-stu-id="afef2-111">We also encrypt credentials before saving them into Accounts.</span></span> <span data-ttu-id="afef2-112">暗号化には **"AES/CBC/PKCS5Padding"** アルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="afef2-112">We use " **AES/CBC/PKCS5Padding** " algorithm for encryption.</span></span> <br/> |<span data-ttu-id="afef2-113">sqlcipher というライブラリをSQL暗号化されたデータベース [に格納します](https://www.zetetic.net/sqlcipher/design/)。</span><span class="sxs-lookup"><span data-stu-id="afef2-113">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/).</span></span> <span data-ttu-id="afef2-114">CBC モードでは、256 ビット AES の既定のアルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="afef2-114">We use their default algorithm of 256-bit AES in CBC mode.</span></span> <span data-ttu-id="afef2-115">保存中のデータは常にデータベース ファイルで暗号化され、アプリの揮発性メモリと呼び出しスタック内で送信される暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="afef2-115">The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks.</span></span> <span data-ttu-id="afef2-116">また、ユーザーの名前とパスワードの暗号化と同じ方法を使用してボイスメール ファイルも暗号化します (これらは DB に保存されません)。</span><span class="sxs-lookup"><span data-stu-id="afef2-116">We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB).</span></span> <span data-ttu-id="afef2-117">ボイスメールは、再生を許可するためにディスク上で一時的に暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="afef2-117">Voicemails are temporarily unencrypted on disk to allow playback.</span></span>  <br/> |<span data-ttu-id="afef2-118">この情報は暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="afef2-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="afef2-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="afef2-119">**iOS**</span></span> <br/> |<span data-ttu-id="afef2-120">キーチェーンのユーザー名/パスワードは暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="afef2-120">We DO NOT encrypt the username/password in the keychain.</span></span> <span data-ttu-id="afef2-121">ただし、キーチェーンは独自に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="afef2-121">The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="afef2-122">アプリ ストレージ内のすべての [ファイルで、既に NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) データ保護フラグを使用しています。</span><span class="sxs-lookup"><span data-stu-id="afef2-122">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage.</span></span> <span data-ttu-id="afef2-123">つまり、ユーザーがデバイスの再起動後に初めてデバイスのロックを解除するまで、アプリ ストレージ内のファイルは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="afef2-123">This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot.</span></span> <br/> |<span data-ttu-id="afef2-124">この情報は暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="afef2-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="afef2-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="afef2-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="afef2-126">Windows Phone では、Windows の DPAPI (Data Protection API) を使用してパスワードを保護します。</span><span class="sxs-lookup"><span data-stu-id="afef2-126">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords.</span></span> <span data-ttu-id="afef2-127">使用される暗号化スキームは AES だと思います。</span><span class="sxs-lookup"><span data-stu-id="afef2-127">I believe the encryption scheme used is AES.</span></span> <span data-ttu-id="afef2-128">Windows では、キー サイズ (またはスキーム) を構成するオプションは提供ないので、DPAPI で提供される機能です。</span><span class="sxs-lookup"><span data-stu-id="afef2-128">Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives.</span></span> <span data-ttu-id="afef2-129">デバイスのTPM を使用して、ユーザーとデバイスに固有のキーをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="afef2-129">It will use the device TPM to secure keys which are specific to the user and device.</span></span> <span data-ttu-id="afef2-130">DPAPI キーはアプリに固有のキーではありません。</span><span class="sxs-lookup"><span data-stu-id="afef2-130">Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="afef2-131">WP アプリ データは [、CRED](/previous-versions/windows/apps/hh487164(v=vs.105))のように DPAP I で保護されます。</span><span class="sxs-lookup"><span data-stu-id="afef2-131">WP App Data is protected with [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, like the creds.</span></span> <span data-ttu-id="afef2-132">必要な詳細に応じて、アプリ データのインデックス情報の一部は (非 DPAPI) AES 暗号化によって保護され、塩分け処理を避けるため、暗号化を解除せずに検索できます。そのキーは、順番に DPAPI で保護されます。</span><span class="sxs-lookup"><span data-stu-id="afef2-132">Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI.</span></span> <span data-ttu-id="afef2-133">キャッシュされたデータは、データ フォルダーに到達できると仮定して、同じ電話から任意のプロセスで読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="afef2-133">Cached data can be read by any process from the same phone, assuming it can reach our data folder.</span></span> <span data-ttu-id="afef2-134">Windows 暗号化はサンドボックス違反から保護するのではなく、外部アクセスの試みからのみ行います。</span><span class="sxs-lookup"><span data-stu-id="afef2-134">Windows encryption does not protect from sandbox breach, only external access attempts.</span></span>  <br/> |<span data-ttu-id="afef2-135">この情報は暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="afef2-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="afef2-136">**注:** 上記のモバイル [プラットフォームで利用可能](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) なデバイスピンの適用については、この公開ドキュメントを参照してください</span><span class="sxs-lookup"><span data-stu-id="afef2-136">**Note:** Please refer to [this public documentation](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="afef2-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="afef2-137">Related topics</span></span>
[<span data-ttu-id="afef2-138">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="afef2-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="afef2-139">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="afef2-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
