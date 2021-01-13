---
title: Skype for Business と Office アプリの互換性
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Outlook や他のアプリケーションから Skype for Business の機能にアクセスする方法Microsoft Officeします。
ms.openlocfilehash: b3d792d5e6376e4d845aa74f0585acf7d9a70d81
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802737"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business と Office アプリの互換性
 
Outlook や他のアプリケーションから Skype for Business の機能にアクセスする方法Microsoft Officeします。
  
このトピックでは、Skype for Business とさまざまなバージョンのサービス スイートとの互換性Microsoft Officeします。 
  
## <a name="office-and-skype-for-business"></a>Office and Skype for Business

次の表では、「Skype for Business Server と Exchange Server を統合する」で説明されているとおり、Exchange を展開して統合すると、さまざまなバージョンの Office でサポートされる [Skype for Business](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)の機能について説明します。
  
**Skype for Business と Microsoft Office互換性**

|**機能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015、2016**|**Office 2016 for Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook の機能** ||||
|Outlook 会議出席依頼をカスタマイズする (ロゴ、ヘルプ URL、免責事項、フッター テキストの追加)  |いいえ  |はい   |必要|
|既定で出席者の音声とビデオをミュートする会議オプションを構成する    |いいえ    |はい    |いいえ    |
|Office および Skype for Business 全体で連絡先リストを管理するための統合連絡先ストア    |いいえ    |はい (Exchange 2013 以降が必要)    |必要    |
|高解像度のプロファイル画像    |いいえ    |はい (Exchange 2013 以降が必要)    |必要    |
|Microsoft Outlook の [From]、[To]、および [Cc] フィールドのプレゼンス状態    |はい    |はい    |必要    |
|[空き時間情報] メニューから IM または通話で返信する    |はい (連絡先カードから)    |はい (連絡先カードから)    |はい (連絡先カードから)    |
|[スケジュール アシスタント] タブの会議出席依頼のプレゼンス状態    |はい    |必要    |いいえ    |
|受信した電子メール メッセージのツール バーまたはリボンから IM または通話で返信する    |はい    |はい    |必要    |
|**その他Office アプリ**   ||||
|OneNote の共有ノート    |いいえ    |はい    |いいえ    |
|セットアッププログラムに統合Officeセットアップ    |いいえ    |はい    |いいえ    |
|PowerPoint プレゼンテーションのコンテンツ    |必要    |はい (VBSS も利用可能)    |必要    |
|Microsoft Word および Microsoft Excel ファイルの IM およびプレゼンス表示 (スマート タグが有効)    |Microsoft Word のみ    |Microsoft Word のみ    |いいえ    |
|Microsoft SharePoint サイトの IM およびプレゼンス表示 (Outlook のインストールが必要)    |はい    |必要    |いいえ    |
   
&#x2776; - Skype for Business on Mac クライアントまたは Lync 2011 for Mac クライアントがインストールされ、現在実行されていることを前提とします。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server and Skype for Business

次の表に、さまざまなバージョンの Skype for Business のサポートを示Exchange Server。 Extended MAPI 通話を処理するには、クライアント コンピューターに Outlook がインストールされている必要があり、一部の機能は Exchange Web サービス (EWS) を使用する必要があります。
  
**Skype for Business と Exchange Server互換性**

|**Exchange Server のバージョン**|**Skype for Business のサポート**|
|:-----|:-----|
|Exchange Server 2019 (Skype for Business Server 2019 のみ) |2013 Exchange Serverと同じ    |
|Exchange Server 2016    |2013 Exchange Serverと同じ  <br/> |
|Exchange Server 2013  <br/> |2010 Exchange Serverサポートと同じです。次の機能が追加されています。  <br/>&bull;&nbsp;&nbsp;統合連絡先ストア  <br/>&bull;&nbsp;&nbsp;高解像度の画像  <br/>&bull;&nbsp;&nbsp;アーカイブ統合  <br/> **注:** 詳細については [、「Skype for Business Server と Exchange Server」 を参照してください](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Exchange Server 2010  <br/>(Skype for Business Server 2015 のみ) |次の機能は、EWS を通してのみで使用できます。  <br/>&bull;&nbsp;&nbsp;会話履歴フォルダー内のアイテムの読み取りまたは削除  <br/>&bull;&nbsp;&nbsp;ボイス メール アイテムの読み取りまたは削除  <br/>&bull;&nbsp;&nbsp;拡張空き時間情報と会議の件名と場所を表示する  <br/>&bull;&nbsp;&nbsp;Exchange 連絡先の同期  <br/> パブリック フォルダーは、2010 年Exchange Serverオプションです。  <br/> |
   
## <a name="see-also"></a>関連項目
 
[Windows クライアントの要件とソフトウェア サポート](windows-requirements.md)
  
[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)

