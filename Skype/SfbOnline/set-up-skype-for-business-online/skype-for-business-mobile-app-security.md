---
title: Skype for Business のモバイル アプリのセキュリティ
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'ユーザーのモバイル アプリケーションのセキュリティの設定について説明します。 '
ms.openlocfilehash: 03b6575826defd5bd4c8c7739a1975edaabe0752
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530617"
---
# <a name="skype-for-business-mobile-app-security"></a>Skype for Business のモバイル アプリのセキュリティ

## <a name="skype-for-business-client-security"></a>Skype ビジネス クライアントのセキュリティ

この資料では、ビジネスのモバイル アプリケーションの Skype でのデータ暗号化の情報について説明します。
  
|||||
|:-----|:-----|:-----|:-----|
||**ユーザー名/パスワード** <br/> |**アプリケーション データ (会話、<br/>リスト、会議にお問い合わせください)** <br/> |**診断ログ** <br/> |
|**Android** <br/> |お客様は、Android のアカウントの資格情報を保存します。 アカウントにそれらを保存する前に資格情報を暗号化しても。 暗号化の「 **AES、構造体、PKCS5Padding CBC** 」アルゴリズムを使用します。 <br/> |[Sqlcipher](https://www.zetetic.net/sqlcipher/design/)と呼ばれるライブラリを使用して暗号化された SQL データベースに格納します。 CBC モードでは、256 ビット AES の既定のアルゴリズムを使用します。 データベース ・ ファイルには常に暗号化データおよびアプリケーションの揮発性メモリ、および呼び出しスタック内で転送中に暗号化されていない状態では、のみです。 ユーザー名とパスワードの暗号化 (に格納されていないデータベース内) と同じ方法を使用してボイス メール ファイルを暗号化もできます。 ボイスメールは、ディスクの再生を許可するには一時的に暗号化されます。  <br/> |この情報は暗号化されていません。  <br/> |
|**iOS** <br/> |キーチェーンにユーザー名とパスワードは暗号化されません。 キーチェーンは、独自に暗号化されてがいます。  <br/> |既にアプリケーション記憶域内のすべてのファイルに対してデータの保護フラグを[NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)使用しています。 つまり、ユーザーのデバイスの再起動後に非常に最初に、デバイスのロックを解除するまでアプリケーションの記憶域にファイルを暗号化するとします。 <br/> |この情報は暗号化されていません。  <br/> |
|**Windows Phone** <br/> |Windows Phone は、Windows のパスワードをセキュリティで保護するのに DPAPI (データ保護 API) を使用します。 私は、使用される暗号化方式は AES と考えています。 Windows は承りますので、キーのサイズ (またはスキーム) を構成するオプションは、DPAPI は、どのようなので。 ユーザーとデバイスに固有のキーをセキュリティで保護するのに TPM デバイスを使用します。 DPAPI キーが、アプリケーションに固有ではないことに注意してください。  <br/> |WP アプリのデータが保護されている[DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)で、気に入って、資格情報。 によって必要な量の詳細は、アプリケーション データのインデックス情報の一部は復号化、なし表示できるため、DPAPI を使用してそのキーが保護されている順にあがったりを避けるために (DPAPI ではない) の AES 暗号化で保護されています。 データ フォルダーにアクセスできると仮定した場合、同じ携帯電話からのすべてのプロセスによってキャッシュされたデータを読み取ることができます。 Windows の暗号化はサンド ボックスの侵害から保護されない、外部からのアクセスのみを試みます。  <br/> |この情報は暗号化されていません。  <br/> |
   
**注:** 各モバイル プラットフォームの上で利用可能なデバイスの暗証番号 (pin) 強制については、[このパブリックのドキュメント](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)を参照してください。
  
## <a name="related-topics"></a>関連トピック
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
 