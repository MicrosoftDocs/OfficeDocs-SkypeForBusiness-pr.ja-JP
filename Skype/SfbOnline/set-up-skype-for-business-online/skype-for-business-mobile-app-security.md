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
# <a name="skype-for-business-mobile-app-security"></a>Skype for Business のモバイル アプリのセキュリティ

## <a name="skype-for-business-client-security"></a>Skype for Business クライアントのセキュリティ

この記事では、Skype for Business モバイル アプリのデータ暗号化に関する情報について説明します。
  
|||||
|:-----|:-----|:-----|:-----|
||**ユーザー名/パスワード** <br/> |**アプリ データ (会話、 <br/> 連絡先リスト、会議)** <br/> |**診断ログ** <br/> |
|**Android** <br/> |Android アカウントには資格情報情報が保存されます。 アカウントに保存する前に資格情報も暗号化します。 暗号化には **"AES/CBC/PKCS5Padding"** アルゴリズムを使用します。 <br/> |sqlcipher というライブラリをSQL暗号化されたデータベース [に格納します](https://www.zetetic.net/sqlcipher/design/)。 CBC モードでは、256 ビット AES の既定のアルゴリズムを使用します。 保存中のデータは常にデータベース ファイルで暗号化され、アプリの揮発性メモリと呼び出しスタック内で送信される暗号化されません。 また、ユーザーの名前とパスワードの暗号化と同じ方法を使用してボイスメール ファイルも暗号化します (これらは DB に保存されません)。 ボイスメールは、再生を許可するためにディスク上で一時的に暗号化されません。  <br/> |この情報は暗号化されません。  <br/> |
|**iOS** <br/> |キーチェーンのユーザー名/パスワードは暗号化されません。 ただし、キーチェーンは独自に暗号化されます。  <br/> |アプリ ストレージ内のすべての [ファイルで、既に NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) データ保護フラグを使用しています。 つまり、ユーザーがデバイスの再起動後に初めてデバイスのロックを解除するまで、アプリ ストレージ内のファイルは暗号化されます。 <br/> |この情報は暗号化されません。  <br/> |
|**Windows Phone** <br/> |Windows Phone では、Windows の DPAPI (Data Protection API) を使用してパスワードを保護します。 使用される暗号化スキームは AES だと思います。 Windows では、キー サイズ (またはスキーム) を構成するオプションは提供ないので、DPAPI で提供される機能です。 デバイスのTPM を使用して、ユーザーとデバイスに固有のキーをセキュリティで保護します。 DPAPI キーはアプリに固有のキーではありません。  <br/> |WP アプリ データは [、CRED](/previous-versions/windows/apps/hh487164(v=vs.105))のように DPAP I で保護されます。 必要な詳細に応じて、アプリ データのインデックス情報の一部は (非 DPAPI) AES 暗号化によって保護され、塩分け処理を避けるため、暗号化を解除せずに検索できます。そのキーは、順番に DPAPI で保護されます。 キャッシュされたデータは、データ フォルダーに到達できると仮定して、同じ電話から任意のプロセスで読み取り可能です。 Windows 暗号化はサンドボックス違反から保護するのではなく、外部アクセスの試みからのみ行います。  <br/> |この情報は暗号化されません。  <br/> |
   
**注:** 上記のモバイル [プラットフォームで利用可能](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) なデバイスピンの適用については、この公開ドキュメントを参照してください
  
## <a name="related-topics"></a>関連項目
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
