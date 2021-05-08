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
description: 'ユーザーのモバイル アプリのセキュリティを設定する方法について学習します。 '
ms.openlocfilehash: f600230574b8d16a0f7907b4484da8ffcca6124e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239634"
---
# <a name="skype-for-business-mobile-app-security"></a>Skype for Business のモバイル アプリのセキュリティ

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a>Skype for Businessクライアントのセキュリティ

この記事では、Mobile Apps のデータ暗号化Skype for Business説明します。
  
|||||
|:-----|:-----|:-----|:-----|
||**ユーザー名/パスワード** <br/> |**アプリ データ (会話、 <br/> 連絡先リスト、会議)** <br/> |**診断ログ** <br/> |
|**Android** <br/> |資格情報は Android アカウントに保存されます。 また、資格情報をアカウントに保存する前に暗号化します。 暗号化には **"AES/CBC/PKCS5Padding"** アルゴリズムを使用します。 <br/> |sqlcipher というライブラリをSQL暗号化されたデータベースに[格納します](https://www.zetetic.net/sqlcipher/design/)。 CBC モードでは、256 ビット AES の既定のアルゴリズムを使用します。 保存データは常にデータベース ファイルで暗号化され、アプリの揮発性メモリと呼び出し履歴内の転送中にのみ暗号化されます。 また、ユーザーの名前とパスワード暗号化と同じ方法を使用してボイスメール ファイルを暗号化します (これらは DB に格納されません)。 ボイスメールは、再生を許可するためにディスク上で一時的に暗号化されません。  <br/> |この情報は暗号化されません。  <br/> |
|**iOS** <br/> |キーチェーン内のユーザー名/パスワードは暗号化されません。 ただし、キーチェーンはそれ自身で暗号化されます。  <br/> |アプリ ストレージ内のすべての [ファイルで、NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) データ保護フラグを既に使用しています。 つまり、ユーザーがデバイスの再起動後に初めてデバイスのロックを解除するまで、アプリ ストレージ内のファイルが暗号化されます。 <br/> |この情報は暗号化されません。  <br/> |
|**Windows Phone** <br/> |Windows Phoneパスワードをセキュリティで保護するために、WINDOWS DPAPI (Data Protection API) を使用します。 使用される暗号化スキームは AES だと思います。 Windowsサイズ (スキーム) を構成するオプションは提供しないので、DPAPI が提供する方法です。 デバイス TPM を使用して、ユーザーとデバイスに固有のキーをセキュリティで保護します。 DPAPI キーはアプリに固有ではありません。  <br/> |WP アプリ データは [、CRED](/previous-versions/windows/apps/hh487164(v=vs.105))のように DPAP I で保護されます。 必要な詳細に応じて、アプリ データのインデックス情報の一部は (非 DPAPI) AES 暗号化によって保護され、ソルト処理を回避できます。そのため、暗号化を解除せずに検索し、そのキーは DPAPI で保護されます。 キャッシュされたデータは、データ フォルダーに到達できると仮定して、同じ電話から任意のプロセスで読み取り可能です。 Windows暗号化はサンドボックスの侵害から保護されるのではなく、外部アクセスの試みからのみ保護されます。  <br/> |この情報は暗号化されません。  <br/> |
   
**注:** 上記の [各モバイル プラットフォームで使用可能](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) なデバイス ピンの適用については、このパブリック ドキュメントを参照してください。
  
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
