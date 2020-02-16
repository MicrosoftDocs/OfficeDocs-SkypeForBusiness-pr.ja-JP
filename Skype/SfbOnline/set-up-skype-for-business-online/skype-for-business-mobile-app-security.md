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
description: 'ユーザーにモバイルアプリのセキュリティを設定する方法について説明します。 '
ms.openlocfilehash: 2c22f384196f0f05ca89d6f0e07ae84a1548d78a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010780"
---
# <a name="skype-for-business-mobile-app-security"></a>Skype for Business のモバイル アプリのセキュリティ

## <a name="skype-for-business-client-security"></a>Skype for Business クライアントのセキュリティ

この記事では、Skype for Business モバイルアプリのデータ暗号化の情報について説明します。
  
|||||
|:-----|:-----|:-----|:-----|
||**ユーザー名/パスワード** <br/> |**アプリデータ (スレッド、<br/>連絡先リスト、会議)** <br/> |**診断ログ** <br/> |
|**Android** <br/> |Android アカウントの資格情報を保存します。 また、アカウントに保存する前に、資格情報を暗号化します。 暗号化には " **AES/CBC/PKCS5Padding** " アルゴリズムを使います。 <br/> |[Sqlcipher](https://www.zetetic.net/sqlcipher/design/)というライブラリを使って、暗号化された SQL データベースに保存します。 ここでは、CBC モードで256ビット AES の既定のアルゴリズムを使います。 Rest のデータは常にデータベースファイルで暗号化され、アプリの揮発性メモリと呼び出し履歴内では暗号化されません。 また、ユーザー名とパスワードの暗号化と同じ方法でボイスメールファイルを暗号化します (データベースには保存されません)。 ボイスメールは、一時的にディスクに暗号化されていないため、再生が可能です。  <br/> |この情報は暗号化されません。  <br/> |
|**iOS** <br/> |キーチェーン内のユーザー名とパスワードは暗号化されません。 ただし、キーチェーンは暗号化されています。  <br/> |アプリストレージ内のすべてのファイルに対して、既に[Nsfileprotectioncompleteを](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)使用しています。 つまり、デバイスの再起動後、ユーザーがデバイスのロックを解除するまで、アプリストレージ内のファイルは暗号化されます。 <br/> |この情報は暗号化されません。  <br/> |
|**Windows Phone** <br/> |Windows Phone では、Windows の DPAPI (データ保護 API) を使ってパスワードを保護します。 暗号化スキームは AES であると考えられます。 Windows では、キーサイズ (またはスキーム) を構成するためのオプションを提供していないため、DPAPI によって提供されます。 デバイス TPM を使って、ユーザーとデバイスに固有のキーをセキュリティで保護します。 DPAPI キーはアプリに固有のものではないことに注意してください。  <br/> |WP アプリデータは、資格情報などの[Dpap](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)I によって保護されます。 必要な詳細に応じて、アプリデータのインデックス情報の一部は、ソルトを回避するために (非 DPAPI) AES 暗号化によって保護されているため、解読しなくても、そのキーが DPAPI で保護されていることを意味します。 キャッシュデータは、データフォルダーに到達できるという前提で、同じ電話からどのプロセスでも読み取ることができます。 Windows の暗号化では、サンドボックスのブリーチからは保護されません。外部アクセスの試行のみが対象となります。  <br/> |この情報は暗号化されません。  <br/> |
   
**注:** 上記の各モバイルプラットフォームで使用可能なデバイス pin の適用については、[この公開ドキュメント](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)を参照してください。
  
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
 
