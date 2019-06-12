---
title: Skype for Business の Office アプリとの互換性
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Outlook やその他の Microsoft Office アプリケーションから Skype for Business の機能にアクセスする方法について説明します。
ms.openlocfilehash: c24c6b08e21db357d52b1cc130e53f23b6123ff6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277434"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business の Office アプリとの互換性
 
Outlook やその他の Microsoft Office アプリケーションから Skype for Business の機能にアクセスする方法について説明します。
  
このトピックでは、Microsoft Office スイートのさまざまなバージョンとの Skype for Business の互換性について説明します。 
  
## <a name="office-and-skype-for-business"></a>Office と Skype for Business

次の表では、「 [skype for Business server を Exchange server と統合](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)する」の説明に従って、さまざまなバージョンの Office でサポートされている Skype for business の機能について説明します。
  
**Skype for Business および Microsoft Office の互換性**

|**機能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015、2016**|**Office 2016 For Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook の機能** ||||
|Outlook の会議の招待 (およびロゴ、ヘルプ URL、免責事項、フッター テキスト) をカスタマイズする  |いいえ  |はい   |可|
|会議オプションを構成して、出席者の音声とビデオを既定でミュートする    |いいえ    |あり    |いいえ    |
|Office と Skype for Business で連絡先リストを管理するための統合連絡先ストア    |いいえ    |○ (Exchange 2013 以降が必要)    |はい    |
|高解像度のプロフィール画像    |いいえ    |○ (Exchange 2013 以降が必要)    |はい    |
|Microsoft Outlook の [差出人]、[宛先] および [Cc] フィールドのプレゼンス状態    |はい    |可    |可    |
|状態メニューから IM または通話で返信    |○ (連絡先カードから)    |○ (連絡先カードから)    |○ (連絡先カードから)    |
|[スケジュール アシスタント] タブの会議出席依頼のプレゼンス状態    |はい    |はい    |いいえ    |
|受信した電子メール メッセージのツール バーまたはリボンから、IM または電話で返信    |はい    |可    |可    |
|**その他の Office アプリケーション**   ||||
|OneNote 共有メモ    |いいえ    |あり    |いいえ    |
|Office のセットアップ プログラムに統合されたセットアップ    |不可    |あり    |いいえ    |
|PowerPoint プレゼンテーションのコンテンツ    |はい    |○ (VBSS も利用可能)    |○    |
|Microsoft Word および Microsoft Excel ファイルの IM およびプレゼンス表示 (スマート タグが有効)    |Microsoft Word のみ    |Microsoft Word のみ    |×    |
|Microsoft SharePoint サイトの IM およびプレゼンス (Outlook のインストールが必要)    |はい    |はい    |いいえ    |
   
&#x2776;-Mac クライアントまたは Lync 2011 for Mac クライアントの Skype for Business がインストールされていて、現在実行されていることを前提としています。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server と Skype for Business

次の表では、さまざまなバージョンの Exchange Server 向けの Skype for Business のサポートについて説明します。 Extended MAPI 通話を処理するには、クライアント コンピューターに Outlook をインストールしておく必要があり、一部の機能には Exchange Web サービス (EWS) が必要です。
  
**Skype for Business と Exchange Server の互換性**

|**Exchange Server のバージョン**|**Skype for Business のサポート**|
|:-----|:-----|
|Exchange Server 2019 (Skype for Business Server 2019 のみ) |Exchange Server 2013 のサポートと同様    |
|Exchange Server 2016    |Exchange Server 2013 のサポートと同様  <br/> |
|Exchange Server 2013  <br/> |Exchange Server 2010 のサポートと同様で、次の機能を含みます。   <br/>&bull;&nbsp;&nbsp;ユニファイド連絡先の保存  <br/>&bull;&nbsp;&nbsp;高解像度の図  <br/>&bull;&nbsp;&nbsp;アーカイブの統合  <br/> **注:** 詳細については、「 [Skype For Business server と Exchange server の統合](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)」を参照してください。  <br/> |
|Exchange Server 2010  <br/>(Skype for Business Server 2015 のみ) |次の機能は、EWS を通してのみ使用できます。  <br/>&bull;&nbsp;&nbsp;[会話履歴] フォルダー内のアイテムを閲覧または削除する  <br/>&bull;&nbsp;&nbsp;ボイスメールアイテムを閲覧または削除する  <br/>&bull;&nbsp;&nbsp;延長された空き時間情報と会議の件名と場所を表示する  <br/>&bull;&nbsp;&nbsp;Exchange の連絡先の同期  <br/> Exchange Server 2010 で、パブリック フォルダーはオプションです。  <br/> |
   
## <a name="see-also"></a>関連項目
 
[Windows クライアントの要件およびソフトウェア サポート](windows-requirements.md)
  
[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)

