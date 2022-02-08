---
title: Windows クライアントの要件とソフトウェア サポート
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: '概要: クライアント サポート要件Windows計画中に、クライアント サポート要件を確認Skype for Business Server。'
ms.openlocfilehash: 50b0583e55c872e15e59c8510503b5b11ffc8714
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395009"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows クライアントの要件とソフトウェア サポート
 
**概要:** 計画中Windowsクライアント サポート要件を確認Skype for Business Server。
  
このセクションでは、クライアントのサポートに必要なソフトウェアSkype for Business Windowsします。 これらのクライアントは、Microsoft 365インストールOffice 365インストール時にインストールされ、すべてのデバイスでダウンロード Skype for Business[で利用できます](https://products.office.com/skype-for-business/download-app?tab=tabs-3)。
  
> [!NOTE]
> Skype for Business メッセージングおよびコラボレーション クライアント内からの会議管理をサポートするオンライン 会議アドインは、Outlook と一緒に自動的にインストールSkype for Business。 
  
**クライアントとSkype for Businessアドインに必要なソフトウェア**

|**システム コンポーネント**|**サポートされるバージョン**|
|:-----|:-----|
|Windows オペレーティング システム  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windowsサービス パックを使用して Server 2008 R2 以降をインストールする  <br/> **注:** Skype for Businessおよびオンライン 会議アドイン for Skype for Businessは、Windows Vista または Windows XP (任意のバージョン) ではサポートされていません。 <br/> |
|インストールと更新  <br/> |管理者の権限およびアクセス許可  <br/> |
|ブラウザー  <br/> |Microsoft Edge  <br/> Internet Explorer 11 インターネット ブラウザー  <br/>  Internet Explorer 10インターネット ブラウザー <br/> Internet Explorer 9 ブラウザー  <br/> Internet Explorer 8インターネット ブラウザー  <br/> Internet Explorer 7 インターネット ブラウザー  <br/> Mozilla Firefox Web ブラウザー  <br/>  Google Chrome Web ブラウザー  <br/>**注:** 認証 HTTP プロキシをSkype for Business Microsoft Exchange Online組織が HTTP プロキシを展開している場合は、Internet Explorer 8以降が必要です。           |
|Microsoft Office Integration  <br/> | Outlook 2010 以降 |
|Microsoft Exchange 統合  <br/> | Microsoft Exchange Server 2010 以降  | 
   
## <a name="hardware"></a>ハードウェア

クライアントの実行にMicrosoft 365ハードウェアOffice[システム](https://products.office.com/office-system-requirements)要件の詳細については、「Skype for Business」をSkype for Businessしてください。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype会議アプリと会議Skype for Business Web アプリ 

[Skypeの会議アプリとSkype for Business Web アプリは、オペレーティング システムとブラウザーの特定の組み合わせをサポートします。 詳細については、「 [Plan for Meetings clients (Web App and Meetings App)」を参照してください](meetings-clients.md)。 
  
## <a name="using-mandatory-profiles"></a>固定プロファイルの使用

電話会議機能を使用するSkype for Business場合は、Active Directory ドメイン サービスの必須プロファイルを使用してクライアントにサインインSkype for Businessしてください。 必須プロファイルは読み取り専用のユーザー プロファイルなので、Skype for Business 会議に必要な公開キー基盤 (PKI) キーをプロファイルに保存することはできません。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Windows Phone 版 Skype for Business のシステム要件
 
 
Microsoft Skype for Business for Windows Phoneは、スマートフォンまたはモバイル デバイスから接続している組織内のユーザーにインスタント メッセージング (IM)、拡張プレゼンス、テレフォニー Windows Professional提供します。 モバイル デバイスを使用すると、ユーザーはモバイル デバイスのSkype for Business。 このトピックでは、前提条件と技術的要件Skype for Business for Windows Phone必要なコンポーネント、展開のガイダンスを識別する方法を含む、アプリケーションの計画に関する考慮事項について説明します。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype for Business for Windows Phone前提条件

以下に、前提条件Skype for Business for Windows Phone示します。
  
- Windows Phone 8.1 以降。
    
- デバイスWindows Phone Microsoft から最新の更新プログラムを利用できる必要があります。 詳細については、「Windows Phone 8.1」の「Windows Phone[」を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=281961)。
    
- デバイスには 22 MB の使用可能なディスク領域が必要です。
    
- ユーザーは、利用している通信事業者の音声およびデータ通信プランが必要です。


## <a name="see-also"></a>関連項目

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)
  
[Mac 版 Skype for Business クライアントの要件](mac-requirements.md)

[すべてのデバイスSkype for Businessダウンロードする](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365およびOffice要件](https://products.office.com/office-system-requirements)
