---
title: Windows クライアントの要件およびソフトウェア サポート
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
ms.openlocfilehash: a66887b616461a40c6326a66d982a8bfbe8e9605
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803487"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows クライアントの要件およびソフトウェア サポート
 
**概要:** Skype for Business Server を計画しているときに、Windows クライアントのサポート要件を確認します。
  
このセクションでは、Skype for Business Windows クライアントをサポートするために必要なソフトウェアについて説明します。  これらのクライアントは、Office 365 のインストール時にインストールされ、[すべてのデバイスで Skype For business をダウンロード](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)するときにも使用できます。
  
> [!NOTE]
> Skype for business のオンライン会議アドインは、Outlook メッセージングおよびコラボレーションクライアント内からの会議管理をサポートしており、Skype for Business で自動的にインストールされます。 
  
**Skype for Business クライアントとオンライン会議アドインに必要なソフトウェア**

|**システム コンポーネント**|**サポートされているバージョン**|
|:-----|:-----|
|Windows オペレーティングシステム  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Windows 7 オペレーティング システム  <br/> 最新の service pack を搭載した Windows Server 2008 R2 以降  <br/> **注:** Skype for business と Skype for Business のオンライン会議アドインは、Windows Vista または Windows XP (すべてのバージョン) ではサポートされていません。 <br/> |
|インストールと更新  <br/> |管理者の権限およびアクセス許可  <br/> |
|ブラウザー  <br/> |Microsoft Edge  <br/> Internet Explorer 11 インターネットブラウザー  <br/>  Internet Explorer 10 インターネットブラウザー <br/> Internet Explorer 9 Internet browser  <br/> Internet Explorer 8 インターネットブラウザー  <br/> Internet Explorer 7 インターネットブラウザー  <br/> Mozilla Firefox Web ブラウザー  <br/>  Google Chrome web ブラウザー  <br/>**注:** Microsoft Exchange Online で Skype for Business を使用していて、認証用の HTTP プロキシが組織で展開されている場合は、Internet Explorer 8 以降が必要です。           |
|Microsoft Office Integration  <br/> | Outlook 2010 以降 |
|Microsoft Exchange 統合  <br/> | Microsoft Exchange Server 2010 以降  | 
   
## <a name="hardware"></a>ハードウェア

Skype for Business クライアントを実行するために必要なハードウェアの Office 365[システム要件](https://products.office.com/en-us/office-system-requirements)を参照してください。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 会議アプリと Skype for Business Web App 

Skype 会議アプリと Skype for Business Web App は、オペレーティングシステムとブラウザーの特定の組み合わせをサポートしています。 詳細については、「[会議クライアント (Web アプリと会議アプリ) の計画](meetings-clients.md)」を参照してください。 
  
## <a name="using-mandatory-profiles"></a>固定プロファイルの使用

Skype for Business 会議機能の使用を計画している場合は、Active Directory ドメインサービスの必須プロファイルを使用して Skype for Business クライアントにサインインしないようにしてください。 必須プロファイルは読み取り専用のユーザープロファイルであるため、Skype for Business 会議に必要な公開キー基盤 (PKI) キーをプロファイルに保存することはできません。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Windows Phone 版 Skype for Business のシステム要件
 
 
Microsoft Skype for Business for Windows Phone は、スマートフォンまたは Windows Professional モバイルデバイスから接続している組織内のユーザーに対してインスタントメッセージング (IM)、拡張プレゼンス、およびテレフォニーを提供します。 モバイルデバイスを使用すると、ユーザーは Skype for Business の利用可能範囲を拡張できます。 このトピックでは、前提条件と技術要件、必要なコンポーネント、展開のガイダンスなど、Skype for Business for Windows Phone の計画に関する考慮事項について説明します。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Windows Phone 版 Skype for Business の前提要件

次に、Windows Phone 版 Skype for Business の前提条件を示します。
  
- Windows Phone 8.1 以降。
    
- Windows Phone デバイスには、Microsoft から入手できる最新の更新プログラムが必要です。 詳細については、「windows phone [8 の更新履歴](https://go.microsoft.com/fwlink/p/?LinkID=281961)」の「windows phone 8.1」セクションを参照してください。
    
- デバイスには、22 MB の空き領域が必要です。
    
- ユーザーは、利用している通信事業者の音声およびデータ通信プランが必要です。


## <a name="see-also"></a>関連項目

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)
  
[Skype for Business on Mac クライアントの要件](mac-requirements.md)

[すべてのデバイスで Skype for Business をダウンロードする](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 システム要件](https://products.office.com/en-us/office-system-requirements)
