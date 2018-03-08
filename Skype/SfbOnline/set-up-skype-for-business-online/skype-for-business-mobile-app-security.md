---
title: "Skype for Business のモバイル アプリのセキュリティ"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
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
description: "ユーザーのモバイル アプリのセキュリティを設定する方法を学習します。 "
ms.openlocfilehash: 150eb50c4e2c57b3e51b9400d9fdb79d49990174
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="4da44-103">Skype for Business のモバイル アプリのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4da44-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="4da44-104">Skype for Business クライアントのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4da44-104">Skype for Business Client Security</span></span>

<span data-ttu-id="4da44-105">この記事で Skype for Business のモバイル アプリのデータ暗号化情報をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4da44-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="4da44-106">**ユーザー名とパスワードを入力**</span><span class="sxs-lookup"><span data-stu-id="4da44-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="4da44-107">**アプリのデータ (会話、<br/>連絡先リスト、会議)**</span><span class="sxs-lookup"><span data-stu-id="4da44-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="4da44-108">**診断ログ**</span><span class="sxs-lookup"><span data-stu-id="4da44-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="4da44-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="4da44-109">**Android**</span></span> <br/> |<span data-ttu-id="4da44-p101">Android のアカウントの資格情報を保存するとします。資格情報を暗号化するのには、アカウントに保存する前にします。暗号化の" **AES/CBC/PKCS5Padding** "アルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="4da44-p101">We store credentials information in Android Accounts. We also encrypt credentials before saving them into Accounts. We use " **AES/CBC/PKCS5Padding** " algorithm for encryption. </span></span><br/> |<span data-ttu-id="4da44-p102">[Sqlcipher](https://www.zetetic.net/sqlcipher/design/)と呼ばれるライブラリを使用して暗号化された SQL データベースに格納します。CBC モードで、既定のアルゴリズムの 256 ビット AES を使用します。残りのデータは、データベース ファイルには常に暗号化し、アプリの揮発性メモリと通話履歴内の送信中には、暗号化のみします。ボイス メールのファイルと同じ方法を使用して、ユーザー名とパスワードの暗号化 (が格納されていないデータベース内) を暗号化することもできます。ボイスメールは、再生を許可するディスク一時的に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="4da44-p102">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/). We use their default algorithm of 256-bit AES in CBC mode. The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks. We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB). Voicemails are temporarily unencrypted on disk to allow playback.  </span></span><br/> |<span data-ttu-id="4da44-118">この情報が暗号化されていません。</span><span class="sxs-lookup"><span data-stu-id="4da44-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="4da44-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="4da44-119">**iOS**</span></span> <br/> |<span data-ttu-id="4da44-p103">キーチェーン内のユーザー名とパスワードが暗号化されません。キーチェーン、暗号化、ただし、独自にされます。</span><span class="sxs-lookup"><span data-stu-id="4da44-p103">We DO NOT encrypt the username/password in the keychain. The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="4da44-p104">既にアプリの記憶域にすべてのファイルに[NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)データ保護フラグ使用しています。ユーザーを非常に初めて、デバイスを再起動した後、デバイスのロックを解除するまでアプリの記憶域にファイルを暗号化するようになります。</span><span class="sxs-lookup"><span data-stu-id="4da44-p104">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage. This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot. </span></span><br/> |<span data-ttu-id="4da44-124">この情報が暗号化されていません。</span><span class="sxs-lookup"><span data-stu-id="4da44-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="4da44-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="4da44-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="4da44-p105">Windows Phone は、Windows のパスワードをセキュリティで保護された DPAPI (データ保護 API) を使用します。使用する暗号化方式は AES と考えています。Windows しないご意見ご感想のキー サイズ (またはパターン) を構成するためのオプションを DPAPI では、そのようにします。ユーザーとデバイスに固有のキーをセキュリティで保護された TPM デバイスを使用します。DPAPI キーがアプリに固有でないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4da44-p105">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords. I believe the encryption scheme used is AES. Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives. It will use the device TPM to secure keys which are specific to the user and device. Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="4da44-p106">グループのアプリのデータが保護されているなどは、[資格情報の[DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)とします。によっては、どの程度詳しくには、暗号化を解除すると、しないでを検索でき、そのキーが順番に DPAPI で保護されている、あがったりを防ぐために (DPAPI ではない) AES 暗号化でアプリのデータのインデックス情報の一部保護されます。キャッシュされたデータは、データ フォルダーにアクセスできる場合、同じスマート フォンから任意のプロセスの内容を表示できます。Windows 暗号化がサンド ボックス違反から保護することはできません、外部アクセスのみを試みます。</span><span class="sxs-lookup"><span data-stu-id="4da44-p106">WP App Data is protected with [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, like the creds. Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI. Cached data can be read by any process from the same phone, assuming it can reach our data folder. Windows encryption does not protect from sandbox breach, only external access attempts.  </span></span><br/> |<span data-ttu-id="4da44-135">この情報が暗号化されていません。</span><span class="sxs-lookup"><span data-stu-id="4da44-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="4da44-136">**メモ:**各モバイル プラットフォーム上で使用できるデバイスの暗証番号 (pin) 強制の[この一般向けのドキュメント](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4da44-136">**Note:** Please refer to [this public documentation](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4da44-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4da44-137">Related topics</span></span>
[<span data-ttu-id="4da44-138">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="4da44-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="4da44-139">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4da44-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
