---
title: "Skype for Business のモバイル アプリのセキュリティ"
ms.author: kenwith
author: kenwith
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: concetpual
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
description: ""
---

# Skype for Business のモバイル アプリのセキュリティ

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](d2be8c74-3ba2-4b2d-9807-634904e1f0e8.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/d2be8c74-3ba2-4b2d-9807-634904e1f0e8)をクリックしてください。 
  
## Skype for Business クライアントのセキュリティ

ここでは、Skype for Business モバイル アプリのデータ暗号化の情報について説明します。
  
|||||
|:-----|:-----|:-----|:-----|
||**ユーザー名/パスワード** <br/> |**アプリ データ (会話、連絡先リスト、会議)** <br/> |**診断ログ** <br/> |
|**Android** <br/> |資格情報は Android アカウントに格納します。資格情報は暗号化されてから、アカウントに保存されます。暗号化には " **AES/CBC/PKCS5Padding** " アルゴリズムが使用されます。 <br/> |[sqlcipher](https://www.zetetic.net/sqlcipher/design/) と呼ばれるライブラリーを使用して、暗号化された SQL データベースに格納します。これらの既定のアルゴリズムである 256-bit AES を CBC モードで使用します。保存データは常にデータベース ファイルに暗号化され、アプリの揮発性メモリーおよびコール スタックの中で送信中にのみ暗号化が解除されます。ボイスメール ファイルはユーザー名とパスワードの暗号化と同じ方法で暗号化されます (DB には保存されません)。ボイスメールはディスク上で一時的に暗号化が解除され、再生が許可されます。 <br/> |この情報は暗号化されません。  <br/> |
|**iOS** <br/> |キーチェーン内のユーザー名/パスワードは暗号化されません。 ただし、キーチェーン自体は暗号化されます。  <br/> |アプリ ストレージのすべてのファイルに対して既に [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) データ保護フラグを使用しています。これにより、アプリ ストレージのファイルは、ユーザーがデバイス再起動後に初めてデバイスをロック解除するまで暗号化されることになります。 <br/> |この情報は暗号化されません。  <br/> |
|**Windows Phone** <br/> |Windows Phone では、Windows の DPAPI (データ保護 API) によってパスワードがセキュリティ保護されます。 使用される暗号化スキームは AES であると考えられます。 Windows ではキー サイズ (またはスキーム) を設定するオプションはなく、DPAPI が提供する設定がすべてです。 デバイスの TPM を使用して、ユーザーとデバイスに固有のキーをセキュリティ保護します。 DPAPI キーはアプリに固有ではありませんのでご注意ください。  <br/> |WP アプリ データは、資格情報のように [DPAPI](https://msdn.microsoft.com/ja-jp/library/windows/apps/hh487164%28v=vs.105%29.aspx) で保護されています。どの程度の詳細な情報が必要かに応じて、アプリ データの一部のインデックス情報は (DPAPI ではなく) AES 暗号化で保護され、ソルト処理が回避されます。このため、暗号化を解除することなく、検索することが可能で、キーは順次 DPAPI によって保護されます。キャッシュ データは、同じ電話からの任意のプロセスで読み取ることができ、データ フォルダーに到達できるものと想定されます。Windows の暗号化によってサンドボックス侵害から保護されるわけではなく、外部からのアクセス試行のみが保護の対象となります。 <br/> |この情報は暗号化されません。  <br/> |
   
メモ: 上述の各モバイル プラットフォームで使用できるデバイスの暗証番号 (PIN) の強制適用については、[この公開ドキュメント](https://docs.microsoft.com/ja-jp/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)をご覧ください
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  

