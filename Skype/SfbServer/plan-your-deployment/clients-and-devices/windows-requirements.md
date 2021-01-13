---
title: Windows クライアントの要件とソフトウェア サポート
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server の計画時に、Windows クライアントのサポート要件を確認します。'
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816067"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows クライアントの要件とソフトウェア サポート
 
**概要:** Skype for Business Server の計画時に、Windows クライアントのサポート要件を確認します。
  
このセクションでは、Skype for Business Windows クライアントをサポートするために必要なソフトウェアの概要を示します。 これらのクライアントは、Microsoft 365 または Office 365 のインストール時にインストールされ、すべてのデバイスで [Skype for Business](https://products.office.com/skype-for-business/download-app?tab=tabs-3)をダウンロードすることもできます。
  
> [!NOTE]
> Outlook メッセージングおよびコラボレーション クライアント内からの会議管理をサポートする Skype for Business 用オンライン 会議アドインは、Skype for Business と一緒に自動的にインストールされます。 
  
**Skype for Business クライアントとオンライン会議アドインに必要なソフトウェア**

|**システム コンポーネント**|**サポートされるバージョン**|
|:-----|:-----|
|Windows オペレーティング システム  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2サービス パックを使用する場合  <br/> **注:** Skype for Business と Skype for Business 用オンライン 会議アドインは、Windows Vista または Windows XP (任意のバージョン) ではサポートされていません。 <br/> |
|インストールと更新  <br/> |管理者の権限およびアクセス許可  <br/> |
|ブラウザー  <br/> |Microsoft Edge  <br/> Internet Explorer 11 インターネット ブラウザー  <br/>  Internet Explorer 10 インターネット ブラウザー <br/> Internet Explorer 9 インターネット ブラウザー  <br/> Internet Explorer 8 インターネット ブラウザー  <br/> Internet Explorer 7 インターネット ブラウザー  <br/> Mozilla Firefox Web ブラウザー  <br/>  Google Chrome Web ブラウザー  <br/>**注:** Skype for Business を Microsoft Exchange Online と一緒に使用し、組織が認証 HTTP プロキシを展開している場合は、Internet Explorer 8以降が必要です。           |
|Microsoft Office Integration  <br/> | Outlook 2010 以降 |
|Microsoft Exchange 統合  <br/> | Microsoft Exchange Server 2010 以降  | 
   
## <a name="hardware"></a>ハードウェア

Skype for Business クライアントを実行するために [必要Office](https://products.office.com/office-system-requirements) Microsoft 365 およびシステム要件を参照してください。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 会議アプリと Skype for Business Web App 

Skype 会議アプリと Skype for Business Web App は、オペレーティング システムとブラウザーの特定の組み合わせをサポートします。 詳細については [、「Plan for Meetings clients (Web App and Meetings App)」を参照してください](meetings-clients.md)。 
  
## <a name="using-mandatory-profiles"></a>固定プロファイルの使用

Skype for Business 会議機能を使用する場合は、Active Directory ドメイン サービスの必須プロファイルを使用して Skype for Business クライアントにサインインしないようにします。 必須プロファイルは読み取り専用のユーザー プロファイルなので、Skype for Business 会議に必要な公開キー基盤 (PKI) キーをプロファイルに保存することはできません。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Windows Phone 版 Skype for Business のシステム要件
 
 
Microsoft Skype for Business for Windows Phone は、スマートフォンまたは Windows Professional モバイル デバイスから接続している組織内のユーザーに、インスタント メッセージング (IM)、拡張プレゼンス、およびテレフォニーを提供します。 モバイル デバイスを使用すると、ユーザーは Skype for Business の利用を拡大できます。 このトピックでは、前提条件と技術要件の特定、必要なコンポーネント、展開ガイダンスなど、Skype for Business for Windows Phone の計画に関する考慮事項について説明します。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype for Business for Windows Phone の前提条件

Skype for Business for Windows Phone の前提条件は次のとおりです。
  
- Windows Phone 8.1 以降。
    
- Windows Phone デバイスには、Microsoft から利用可能な最新の更新プログラムが必要です。 詳細については、Windows Phone 8 の更新履歴の [「Windows Phone 8.1」セクションを参照してください](https://go.microsoft.com/fwlink/p/?LinkID=281961)。
    
- デバイスには、22 MB の空きディスク領域が必要です。
    
- ユーザーは、利用している通信事業者の音声およびデータ通信プランが必要です。


## <a name="see-also"></a>関連項目

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)
  
[Mac 版 Skype for Business クライアントの要件](mac-requirements.md)

[すべてのデバイスで Skype for Business をダウンロードする](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 とOfficeの要件](https://products.office.com/office-system-requirements)
