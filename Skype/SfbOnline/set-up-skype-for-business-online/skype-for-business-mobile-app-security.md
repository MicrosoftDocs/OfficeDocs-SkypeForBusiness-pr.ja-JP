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
f1keywords: None
ms.custom:
- Setup
description: 'ユーザーにモバイルアプリのセキュリティを設定する方法について説明します。 '
ms.openlocfilehash: 109fd6cb2ddccbc69ddae3e912506836ee49a399
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285136"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="a84eb-103">Skype for Business のモバイル アプリのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a84eb-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="a84eb-104">Skype for Business クライアントのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a84eb-104">Skype for Business Client Security</span></span>

<span data-ttu-id="a84eb-105">この記事では、Skype for Business モバイルアプリのデータ暗号化の情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="a84eb-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="a84eb-106">**ユーザー名/パスワード**</span><span class="sxs-lookup"><span data-stu-id="a84eb-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="a84eb-107">**アプリデータ (スレッド、<br/>連絡先リスト、会議)**</span><span class="sxs-lookup"><span data-stu-id="a84eb-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="a84eb-108">**診断ログ**</span><span class="sxs-lookup"><span data-stu-id="a84eb-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="a84eb-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="a84eb-109">**Android**</span></span> <br/> |<span data-ttu-id="a84eb-110">Android アカウントの資格情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="a84eb-110">We store credentials information in Android Accounts.</span></span> <span data-ttu-id="a84eb-111">また、アカウントに保存する前に、資格情報を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="a84eb-111">We also encrypt credentials before saving them into Accounts.</span></span> <span data-ttu-id="a84eb-112">暗号化には " **AES/CBC/PKCS5Padding** " アルゴリズムを使います。</span><span class="sxs-lookup"><span data-stu-id="a84eb-112">We use " **AES/CBC/PKCS5Padding** " algorithm for encryption.</span></span> <br/> |<span data-ttu-id="a84eb-113">[Sqlcipher](https://www.zetetic.net/sqlcipher/design/)というライブラリを使って、暗号化された SQL データベースに保存します。</span><span class="sxs-lookup"><span data-stu-id="a84eb-113">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/).</span></span> <span data-ttu-id="a84eb-114">ここでは、CBC モードで256ビット AES の既定のアルゴリズムを使います。</span><span class="sxs-lookup"><span data-stu-id="a84eb-114">We use their default algorithm of 256-bit AES in CBC mode.</span></span> <span data-ttu-id="a84eb-115">Rest のデータは常にデータベースファイルで暗号化され、アプリの揮発性メモリと呼び出し履歴内では暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="a84eb-115">The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks.</span></span> <span data-ttu-id="a84eb-116">また、ユーザー名とパスワードの暗号化と同じ方法でボイスメールファイルを暗号化します (データベースには保存されません)。</span><span class="sxs-lookup"><span data-stu-id="a84eb-116">We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB).</span></span> <span data-ttu-id="a84eb-117">ボイスメールは、一時的にディスクに暗号化されていないため、再生が可能です。</span><span class="sxs-lookup"><span data-stu-id="a84eb-117">Voicemails are temporarily unencrypted on disk to allow playback.</span></span>  <br/> |<span data-ttu-id="a84eb-118">この情報は暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="a84eb-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="a84eb-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="a84eb-119">**iOS**</span></span> <br/> |<span data-ttu-id="a84eb-120">キーチェーン内のユーザー名とパスワードは暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="a84eb-120">We DO NOT encrypt the username/password in the keychain.</span></span> <span data-ttu-id="a84eb-121">ただし、キーチェーンは暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="a84eb-121">The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="a84eb-122">アプリストレージ内のすべてのファイルに対して、既に[Nsfileprotectioncompleteを](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)使用しています。</span><span class="sxs-lookup"><span data-stu-id="a84eb-122">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage.</span></span> <span data-ttu-id="a84eb-123">つまり、デバイスの再起動後、ユーザーがデバイスのロックを解除するまで、アプリストレージ内のファイルは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a84eb-123">This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot.</span></span> <br/> |<span data-ttu-id="a84eb-124">この情報は暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="a84eb-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="a84eb-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="a84eb-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="a84eb-126">Windows Phone では、Windows の DPAPI (データ保護 API) を使ってパスワードを保護します。</span><span class="sxs-lookup"><span data-stu-id="a84eb-126">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords.</span></span> <span data-ttu-id="a84eb-127">暗号化スキームは AES であると考えられます。</span><span class="sxs-lookup"><span data-stu-id="a84eb-127">I believe the encryption scheme used is AES.</span></span> <span data-ttu-id="a84eb-128">Windows では、キーサイズ (またはスキーム) を構成するためのオプションを提供していないため、DPAPI によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="a84eb-128">Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives.</span></span> <span data-ttu-id="a84eb-129">デバイス TPM を使って、ユーザーとデバイスに固有のキーをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="a84eb-129">It will use the device TPM to secure keys which are specific to the user and device.</span></span> <span data-ttu-id="a84eb-130">DPAPI キーはアプリに固有のものではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a84eb-130">Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="a84eb-131">WP アプリデータは、資格情報などの[Dpap](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I によって保護されます。</span><span class="sxs-lookup"><span data-stu-id="a84eb-131">WP App Data is protected with [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, like the creds.</span></span> <span data-ttu-id="a84eb-132">必要な詳細に応じて、アプリデータのインデックス情報の一部は、ソルトを回避するために (非 DPAPI) AES 暗号化によって保護されているため、解読しなくても、そのキーが DPAPI で保護されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a84eb-132">Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI.</span></span> <span data-ttu-id="a84eb-133">キャッシュデータは、データフォルダーに到達できるという前提で、同じ電話からどのプロセスでも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="a84eb-133">Cached data can be read by any process from the same phone, assuming it can reach our data folder.</span></span> <span data-ttu-id="a84eb-134">Windows の暗号化では、サンドボックスのブリーチからは保護されません。外部アクセスの試行のみが対象となります。</span><span class="sxs-lookup"><span data-stu-id="a84eb-134">Windows encryption does not protect from sandbox breach, only external access attempts.</span></span>  <br/> |<span data-ttu-id="a84eb-135">この情報は暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="a84eb-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="a84eb-136">**注:** 上記の各モバイルプラットフォームで使用可能なデバイス pin の適用については、[この公開ドキュメント](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a84eb-136">**Note:** Please refer to [this public documentation](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a84eb-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a84eb-137">Related topics</span></span>
[<span data-ttu-id="a84eb-138">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="a84eb-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a84eb-139">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="a84eb-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
