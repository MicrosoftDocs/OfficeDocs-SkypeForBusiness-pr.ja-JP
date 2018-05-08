---
title: Windows クライアントの要件およびソフトウェア サポート
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: '概要: ビジネス サーバー 2015 の Skype を計画するときに Windows クライアントのサポート要件を確認します。'
ms.openlocfilehash: 3dac3a8e15e53cec5605aa2b003150f491d8f2b5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="windows-client-requirements-and-software-support"></a>Windows クライアントの要件およびソフトウェア サポート
 
**の概要:** ビジネス サーバー 2015 の Skype を計画するときに Windows クライアントのサポート要件を確認します。
  
このセクションでは、Skype をビジネス 2015年、2016 の Windows クライアントのサポートに必要なソフトウェアをまとめたものです。
  
Office 365 をインストールするときにこれらのクライアントがインストールされても、[すべてのデバイスでのビジネス用の Skype のダウンロード](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)で利用可能とします。
  
> [!NOTE]
> Outlook メッセージングおよびコラボレーション クライアント内から会議の管理をサポートするには、ビジネス用の Skype のオンライン会議アドインがビジネスのための Skype で自動的にインストールされます。 
  
**Skype ビジネスとオンライン会議を追加で、Skype のビジネスのために必要なソフトウェア**


|**システム コンポーネント**|**サポートされているバージョン**|
|:-----|:-----|
|Windows オペレーティング システム  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Windows 7 オペレーティング システム  <br/> 最新のサービス パックで Windows Server 2008 R2 の  <br/> **注:** ビジネス用の Skype と Skype ビジネスのオンライン会議アドインでは、Windows Vista または Windows XP (任意のバージョンではサポートされていません。 <br/> |
|インストールと更新  <br/> |管理者の権限およびアクセス許可  <br/> |
|ブラウザー  <br/> |Microsoft Edge  <br/> Internet Explorer 11 インターネット ブラウザー  <br/>  インターネット エクスプ ローラー 10 インターネット ・ ブラウザー <br/> Internet Explorer 9 のインターネット ブラウザー  <br/> Internet Explorer 8 のインターネット ブラウザー  <br/> Internet Explorer 7 のインターネット ブラウザー  <br/> Mozilla Firefox Web ブラウザー  <br/> **注:** ビジネスの Skype を使用している場合と、Microsoft Exchange Online 組織認証の HTTP プロキシ、Internet Explorer 8 の展開がまたは後で必要です。           |
|Microsoft Office Integration  <br/> |統合機能の完全なセットの場合:  <br/> • 2016 の outlook メッセージングおよびコラボレーション クライアント  <br/> • Outlook 2013 のメッセージングおよびコラボレーション クライアント  <br/> • Outlook 2010 のメッセージングおよびコラボレーション クライアント  <br/> |
|Microsoft Exchange 統合  <br/> |• Microsoft Exchange Server 2016  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2010  <br/> |
   
## <a name="hardware"></a>ハードウェア

ビジネス クライアント用の Skype を実行するために必要なハードウェアのための Office 365[のシステム要件](https://products.office.com/en-us/office-system-requirements)を参照してください。
  
## <a name="skype-for-business-web-app-browsers"></a>Skype ビジネス Web アプリケーションのブラウザーの

ビジネス Web アプリケーションの Skype では、特定のオペレーティング システムとブラウザーの組み合わせをサポートします。 詳細については、[計画の会議クライアント (Web アプリケーションおよび会議アプリケーション)](meetings-clients.md)を参照してください。 
  
## <a name="microsoft-office-supportability"></a>Microsoft Office のサポート状況

Skype ビジネス サーバー 2015 クライアントのさまざまなバージョンの Microsoft Office との統合をサポートします。
  
- Skype ビジネス統合機能は、Outlook 2016、Outlook 2013 では、Outlook 2010 でサポートされます。
    
- 2016 の Microsoft Exchange Server、Microsoft Exchange Server 2013、および Microsoft Exchange Server 2010 では、Skype のビジネスの統合機能がサポートされています。
    
- ビジネス用の Skype のオンライン会議アドインがサポートされている Office 2016、Office 2013 では、Microsoft Office 2010年と。
    
## <a name="using-mandatory-profiles"></a>固定プロファイルの使用

ビジネス会議機能は、Skype を使用する場合は、ビジネス クライアント用の Skype にサインインするのには Active Directory ドメイン サービスの固定プロファイルを使用しないようにします。 固定プロファイルは読み取り専用のユーザー プロファイルであるため、Skype のビジネス会議のために必要な公開キー基盤 (PKI) のキーをプロファイルに保存できません。 
  
## <a name="macintosh-operating-systems"></a>Macintosh オペレーティング システム

[Mac クライアントの要件にビジネス用の Skype](mac-requirements.md)では、Mac のサポート要件にビジネス用の Skype が詳しく説明します。
  
## <a name="see-also"></a>関連項目

#### 

[会議クライアント (Web アプリケーションおよび会議アプリケーション) の計画します。](meetings-clients.md)
  
[Mac クライアントの要件にビジネス用の Skype](mac-requirements.md)
#### 

[すべてのデバイスでのビジネス用の Skype をダウンロードします。](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 のシステム要件](https://products.office.com/en-us/office-system-requirements)

