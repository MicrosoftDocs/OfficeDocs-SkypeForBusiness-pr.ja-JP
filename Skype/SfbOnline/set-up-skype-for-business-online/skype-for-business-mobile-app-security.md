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
# <a name="skype-for-business-mobile-app-security"></a>Skype for Business のモバイル アプリのセキュリティ

## <a name="skype-for-business-client-security"></a>Skype for Business クライアントのセキュリティ

この記事で Skype for Business のモバイル アプリのデータ暗号化情報をについて説明します。
  
|||||
|:-----|:-----|:-----|:-----|
||**ユーザー名とパスワードを入力** <br/> |**アプリのデータ (会話、<br/>連絡先リスト、会議)** <br/> |**診断ログ** <br/> |
|**Android** <br/> |Android のアカウントの資格情報を保存するとします。資格情報を暗号化するのには、アカウントに保存する前にします。暗号化の" **AES/CBC/PKCS5Padding** "アルゴリズムを使用します。<br/> |[Sqlcipher](https://www.zetetic.net/sqlcipher/design/)と呼ばれるライブラリを使用して暗号化された SQL データベースに格納します。CBC モードで、既定のアルゴリズムの 256 ビット AES を使用します。残りのデータは、データベース ファイルには常に暗号化し、アプリの揮発性メモリと通話履歴内の送信中には、暗号化のみします。ボイス メールのファイルと同じ方法を使用して、ユーザー名とパスワードの暗号化 (が格納されていないデータベース内) を暗号化することもできます。ボイスメールは、再生を許可するディスク一時的に暗号化されます。<br/> |この情報が暗号化されていません。  <br/> |
|**iOS** <br/> |キーチェーン内のユーザー名とパスワードが暗号化されません。キーチェーン、暗号化、ただし、独自にされます。  <br/> |既にアプリの記憶域にすべてのファイルに[NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)データ保護フラグ使用しています。ユーザーを非常に初めて、デバイスを再起動した後、デバイスのロックを解除するまでアプリの記憶域にファイルを暗号化するようになります。<br/> |この情報が暗号化されていません。  <br/> |
|**Windows Phone** <br/> |Windows Phone は、Windows のパスワードをセキュリティで保護された DPAPI (データ保護 API) を使用します。使用する暗号化方式は AES と考えています。Windows しないご意見ご感想のキー サイズ (またはパターン) を構成するためのオプションを DPAPI では、そのようにします。ユーザーとデバイスに固有のキーをセキュリティで保護された TPM デバイスを使用します。DPAPI キーがアプリに固有でないことに注意してください。  <br/> |グループのアプリのデータが保護されているなどは、[資格情報の[DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)とします。によっては、どの程度詳しくには、暗号化を解除すると、しないでを検索でき、そのキーが順番に DPAPI で保護されている、あがったりを防ぐために (DPAPI ではない) AES 暗号化でアプリのデータのインデックス情報の一部保護されます。キャッシュされたデータは、データ フォルダーにアクセスできる場合、同じスマート フォンから任意のプロセスの内容を表示できます。Windows 暗号化がサンド ボックス違反から保護することはできません、外部アクセスのみを試みます。<br/> |この情報が暗号化されていません。  <br/> |
   
**メモ:**各モバイル プラットフォーム上で使用できるデバイスの暗証番号 (pin) 強制の[この一般向けのドキュメント](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)を参照してください。
  
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップします。](set-up-skype-for-business-online.md)

[ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。](let-skype-for-business-users-add-skype-contacts.md)
