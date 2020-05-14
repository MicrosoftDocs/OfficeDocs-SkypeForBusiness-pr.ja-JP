---
title: Windows クライアントの要件とソフトウェアのサポート
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: '概要: Skype for Business Server の計画中に Windows クライアントのサポート要件を確認します。'
ms.openlocfilehash: 67208fc25344ff417094419f22068822e03b13db
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219827"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows クライアントの要件とソフトウェアのサポート
 
**概要:** Skype for Business Server を計画する際に、Windows クライアントのサポート要件を確認します。
  
このセクションでは、Skype for Business Windows クライアントをサポートするために必要なソフトウェアの概要を示します。 これらのクライアントは、Microsoft 365 または Office 365 のインストール時にインストールされます。また、[すべてのデバイスで Skype For business をダウンロード](https://products.office.com/skype-for-business/download-app?tab=tabs-3)して入手することもできます。
  
> [!NOTE]
> Outlook メッセージングおよびコラボレーションクライアント内から会議管理をサポートする Skype for business 用オンラインミーティングアドインは、Skype for Business と共に自動的にインストールされます。 
  
**Skype for Business クライアントとオンラインミーティングアドインに必要なソフトウェア**

|**システム コンポーネント**|**サポートされているバージョン**|
|:-----|:-----|
|Windows オペレーティングシステム  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 以降の最新の service pack  <br/> **注:** Skype for business と Skype for business のオンライン会議アドインは、Windows Vista または Windows XP (すべてのバージョン) ではサポートされていません。 <br/> |
|インストールと更新  <br/> |管理者の権限およびアクセス許可  <br/> |
|ブラウザー  <br/> |Microsoft Edge  <br/> Internet Explorer 11 インターネットブラウザー  <br/>  Internet Explorer 10 インターネットブラウザー <br/> Internet Explorer 9 インターネットブラウザー  <br/> Internet Explorer 8 インターネットブラウザー  <br/> Internet Explorer 7 インターネットブラウザー  <br/> Mozilla Firefox Web ブラウザー  <br/>  Google Chrome web ブラウザー  <br/>**注:** Microsoft Exchange Online で Skype for Business を使用しており、組織が認証 HTTP プロキシを展開している場合は、Internet Explorer 8 以降が必要です。           |
|Microsoft Office Integration  <br/> | Outlook 2010 以降 |
|Microsoft Exchange 統合  <br/> | Microsoft Exchange Server 2010 以降  | 
   
## <a name="hardware"></a>ハードウェア

Skype for Business クライアントの実行に必要なハードウェアについては、Microsoft 365 および Office[システムの要件](https://products.office.com/office-system-requirements)を参照してください。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 会議アプリと Skype for Business Web App 

Skype 会議アプリと Skype for Business Web アプリは、オペレーティングシステムとブラウザーの特定の組み合わせをサポートします。 詳細については、「 [Plan For 会議クライアント (Web App および会議アプリ)](meetings-clients.md)」を参照してください。 
  
## <a name="using-mandatory-profiles"></a>固定プロファイルの使用

Skype for Business 会議機能の使用を計画している場合は、Active Directory ドメインサービスの必須プロファイルを使用して Skype for business クライアントにサインインすることは避けてください。 固定プロファイルは読み取り専用のユーザープロファイルであるため、Skype for Business 会議に必要な公開キー基盤 (PKI) キーをプロファイルに保存することはできません。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Windows Phone 版 Skype for Business のシステム要件
 
 
Microsoft Skype for Business for Windows Phone は、スマートメッセージング (IM)、拡張プレゼンス、およびテレフォニーを、スマートフォンまたは Windows Professional モバイルデバイスから接続している組織内のユーザーに提供します。 モバイルデバイスを使用すると、ユーザーは Skype for Business のリーチを拡張できます。 このトピックでは、前提条件と技術要件、必要なコンポーネント、および展開ガイダンスを含む、Skype for Business for Windows Phone の計画に関する考慮事項について説明します。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype for Business for Windows Phone の前提条件

Windows Phone for business の必須コンポーネントは次のとおりです。
  
- Windows Phone 8.1 以降。
    
- Windows Phone デバイスには、Microsoft から入手可能な最新の更新プログラムがインストールされている必要があります。 詳細については、「windows phone [8 の更新履歴](https://go.microsoft.com/fwlink/p/?LinkID=281961)」の「windows phone 8.1」セクションを参照してください。
    
- デバイスには、22 MB の使用可能なディスク領域が必要です。
    
- ユーザーは、利用している通信事業者の音声およびデータ通信プランが必要です。


## <a name="see-also"></a>関連項目

[会議クライアントを計画する (Web アプリと会議アプリ)](meetings-clients.md)
  
[Mac クライアント上の Skype for Business の要件](mac-requirements.md)

[すべてのデバイスで Skype for Business をダウンロードする](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 および Office のシステム要件](https://products.office.com/office-system-requirements)
