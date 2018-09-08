---
title: Windows クライアントの要件およびソフトウェア サポート
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: '概要: は、Skype をビジネスのサーバーを計画するときに Windows クライアントのサポート要件を確認します。'
ms.openlocfilehash: 5eda349b18930506e1ff6167804a11ca29c7190a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890981"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows クライアントの要件およびソフトウェア サポート
 
**の概要:** Skype をビジネスのサーバーを計画するときに Windows クライアントのサポート要件を確認します。
  
このセクションでは、Skype をビジネスの Windows クライアントのサポートに必要なソフトウェアをまとめたものです。  Office 365 をインストールするときにこれらのクライアントがインストールされても、[すべてのデバイスでのビジネス用の Skype のダウンロード](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)で利用可能とします。
  
> [!NOTE]
> Outlook メッセージングおよびコラボレーション クライアント内から会議の管理をサポートするには、ビジネス用の Skype のオンライン会議アドインがビジネスのための Skype で自動的にインストールされます。 
  
**ビジネス クライアント用の Skype とオンライン ミーティング アドインに必要なソフトウェア**

|**システム コンポーネント**|**サポートされているバージョン**|
|:-----|:-----|
|Windows オペレーティング システム  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Windows 7 オペレーティング システム  <br/> Windows Server 2008 R2 または最新のサービス パックとそれ以降  <br/> **注:** ビジネス用の Skype と Skype ビジネスのオンライン会議アドインでは、Windows Vista または Windows XP (任意のバージョンではサポートされていません。 <br/> |
|インストールと更新  <br/> |管理者の権限およびアクセス許可  <br/> |
|ブラウザー  <br/> |Microsoft Edge  <br/> Internet Explorer 11 インターネット ブラウザー  <br/>  インターネット エクスプ ローラー 10 インターネット ・ ブラウザー <br/> Internet Explorer 9 のインターネット ブラウザー  <br/> Internet Explorer 8 のインターネット ブラウザー  <br/> Internet Explorer 7 のインターネット ブラウザー  <br/> Mozilla Firefox Web ブラウザー  <br/>  Google Chrome の web ブラウザー  <br/>**注:** ビジネスの Skype を使用している場合と、Microsoft Exchange Online 組織認証の HTTP プロキシ、Internet Explorer 8 の展開がまたは後で必要です。           |
|Microsoft Office Integration  <br/> | Outlook 2010 以降 |
|Microsoft Exchange 統合  <br/> | 2010 またはそれ以降の Microsoft Exchange Server  | 
   
## <a name="hardware"></a>ハードウェア

ビジネス クライアント用の Skype を実行するために必要なハードウェアのための Office 365[のシステム要件](https://products.office.com/en-us/office-system-requirements)を参照してください。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 会議アプリケーションと Web アプリケーションのビジネスの Skype 

Skype 会議アプリケーションおよびビジネス Web アプリケーションの Skype は、特定のオペレーティング システムとブラウザーの組み合わせをサポートします。 詳細については、[計画の会議クライアント (Web アプリケーションおよび会議アプリケーション)](meetings-clients.md)を参照してください。 
  
## <a name="using-mandatory-profiles"></a>固定プロファイルの使用

ビジネス会議機能は、Skype を使用する場合は、ビジネス クライアント用の Skype にサインインするのには Active Directory ドメイン サービスの固定プロファイルを使用しないようにします。 固定プロファイルは読み取り専用のユーザー プロファイルであるため、Skype のビジネス会議のために必要な公開キー基盤 (PKI) のキーをプロファイルに保存できません。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Windows Phone 版 Skype for Business のシステム要件
 
 
Windows Phone のビジネス用の Skype をマイクロソフトでは、スマート フォンや Windows Professional のモバイル デバイスから接続している組織内のユーザーのインスタント メッセージング (IM)、拡張プレゼンス、およびテレフォニーを提供します。 モバイル デバイスは、ビジネスの Skype の範囲を拡張するユーザーを有効にします。 このトピックでは、計画に関する考慮事項 Skype Windows Phone のビジネスの前提条件と技術的な要件、必要なコンポーネント、および展開の手引きの識別を含むについて説明します。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Windows Phone 版 Skype for Business の前提要件

Windows Phone のビジネスの前提条件の Skype を次に示します。
  
- Windows Phone 8.1 以降。
    
- Windows Phone デバイスには、Microsoft から入手できる最新の更新プログラムが必要です。 詳細については、 [Windows Phone 8 の更新履歴](https://go.microsoft.com/fwlink/p/?LinkID=281961)にある Windows Phone 8.1 を参照してください。
    
- デバイスには、22 MB の空き領域が必要です。
    
- ユーザーは、利用している通信事業者の音声およびデータ通信プランが必要です。


## <a name="see-also"></a>関連項目

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)
  
[Mac クライアントの要件にビジネス用の Skype](mac-requirements.md)

[すべてのデバイスでのビジネス用の Skype をダウンロードします。](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 のシステム要件](https://products.office.com/en-us/office-system-requirements)