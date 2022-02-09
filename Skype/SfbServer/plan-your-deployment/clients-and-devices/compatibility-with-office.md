---
title: Skype for Business と Office アプリの互換性
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: アプリケーションや他のアプリケーションからSkype for Business機能Outlookを理解Microsoft Officeします。
ms.openlocfilehash: 249b66eb366d9fa2d5911c24fb7dc88d0dcd6633
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62409900"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business と Office アプリの互換性
 
アプリケーションや他のアプリケーションからSkype for Business機能Outlookを理解Microsoft Officeします。
  
このトピックでは、さまざまなバージョンの Skype for Businessスイートとの互換性についてMicrosoft Officeします。 
  
## <a name="office-and-skype-for-business"></a>OfficeとSkype for Business

次の表は、「Skype for Business Server と Exchange Server を統合する」で説明したように、Office が展開され統合された後に、さまざまなバージョンの Exchange Office でサポートされる Skype for Business 機能について[説明します](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。
  
**Skype for BusinessとMicrosoft Office互換性**

|**機能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015、および 2016**|**Office 2016 for Mac&#x2776;** |
|:-----|:-----|:-----|:-----|
|**Outlook機能** ||||
|会議Outlookをカスタマイズする (ロゴ、ヘルプ URL、免責事項、フッター テキストの追加)  |不要  |はい   |はい|
|出席者の音声とビデオを既定でミュートする会議オプションを構成する    |不要    |はい    |不要    |
|連絡先リストを管理するための統合連絡先ストアOfficeおよびSkype for Business    |不要    |はい (2013 Exchange以降が必要)    |はい    |
|高解像度のプロファイル画像    |不要    |はい (2013 Exchange以降が必要)    |はい    |
|Microsoft Outlook、To、および Cc フィールドのプレゼンス状態    |はい    |はい    |はい    |
|利用可能なメニューから IM または通話で返信する    |はい (連絡先カードから)    |はい (連絡先カードから)    |はい (連絡先カードから)    |
|[スケジュール アシスタント] タブの会議出席依頼のプレゼンス状態    |はい    |はい    |不要    |
|受信した電子メール メッセージのツールバーまたはリボンから IM または通話で返信する    |はい    |はい    |はい    |
|**その他Officeアプリ**   ||||
|OneNote共有メモ    |不要    |はい    |不要    |
|セットアッププログラムに統合Officeセットアップ    |不要    |はい    |不要    |
|PowerPointプレゼンテーション コンテンツ    |はい    |はい (VBSS も利用できます)    |はい    |
|Microsoft Word および Microsoft Excel ファイルの IM およびプレゼンス表示 (スマート タグが有効)    |Microsoft Word のみ    |Microsoft Word のみ    |不要    |
|Microsoft SharePoint サイトの IM およびプレゼンス表示 (Outlook のインストールが必要)    |はい    |はい    |不要    |
   
&#x2776; - Mac クライアントまたは Lync 2011 for Mac クライアントにSkype for Businessインストールされ、現在実行されていることを前提とします。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange ServerとSkype for Business

次の表では、Skype for Businessバージョンのサポートについて説明Exchange Server。 Extended MAPI 通話を処理するには、クライアント コンピューターに Outlook がインストールされている必要があり、一部の機能は Exchange Web サービス (EWS) を使用する必要があります。
  
**Skype for BusinessとExchange Server互換性**

|**Exchange Server のバージョン**|**Skype for Businessサポート**|
|:-----|:-----|
|Exchange Server 2019 (Skype for Business Server 2019 のみ) |2013 Exchange Serverと同じ    |
|Exchange Server 2016    |2013 Exchange Serverと同じ  <br/> |
|Exchange Server 2013  <br/> |2010 Exchange Serverのサポートと同じです。  <br/>&bull;&nbsp;&nbsp;統合連絡先ストア  <br/>&bull;&nbsp;&nbsp;高解像度の画像  <br/>&bull;&nbsp;&nbsp;アーカイブの統合  <br/> **注:** 詳細については、「統合とSkype for Business Server [」をExchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Exchange Server 2010  <br/>(Skype for Business Server 2015 のみ) |次の機能は、EWS を通してのみで使用できます。  <br/>&bull;&nbsp;&nbsp;[会話履歴] フォルダー内のアイテムの読み取りまたは削除  <br/>&bull;&nbsp;&nbsp;ボイス メール アイテムの読み取りまたは削除  <br/>&bull;&nbsp;&nbsp;拡張空き時間情報と会議の件名と場所を表示する  <br/>&bull;&nbsp;&nbsp;Exchange連絡先の同期  <br/> パブリック フォルダーは、2010 年Exchange Serverオプションです。  <br/> |
   
## <a name="see-also"></a>関連項目
 
[Windows クライアントの要件とソフトウェア サポート](windows-requirements.md)
  
[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)

