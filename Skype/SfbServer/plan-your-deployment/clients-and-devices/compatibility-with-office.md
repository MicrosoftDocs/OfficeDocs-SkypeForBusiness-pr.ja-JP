---
title: Skype for Business の Office アプリとの互換性
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Outlook およびその他の Microsoft Office アプリケーションからのビジネス機能の Skype を使用する方法を理解します。
ms.openlocfilehash: c5636b5c7e41b480a9c8aa5532a22523c3554a54
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207476"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business の Office アプリとの互換性
 
Outlook およびその他の Microsoft Office アプリケーションからのビジネス機能の Skype を使用する方法を理解します。
  
このトピックでは、Skype をビジネスのさまざまなバージョンの Microsoft Office スイートとの互換性について説明します。 
  
## <a name="office-and-skype-for-business"></a>Office およびビジネス用の Skype

次の表では、Exchange が展開され、[ビジネス サーバーを Exchange Server との統合の Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)で説明するように統合された後に、Office の各種バージョンでサポートされているビジネス機能の Skype について説明します。
  
**Skype のビジネスと Microsoft Office の互換性**

|**機能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015、2016**|**For Mac Office 2016** & #x 2776。 |
|:-----|:-----|:-----|:-----|
|**Outlook の機能** ||||
|Outlook の会議の招待 (およびロゴ、ヘルプ URL、免責事項、フッター テキスト) をカスタマイズする  |いいえ  |はい   |可|
|会議オプションを構成して、出席者の音声とビデオを既定でミュートする    |いいえ    |あり    |いいえ    |
|Office およびビジネス用の Skype 間での連絡先リストを管理するための統合連絡先ストア    |いいえ    |○ (Exchange 2013 以降が必要)    |はい    |
|高解像度のプロフィールの画像    |いいえ    |○ (Exchange 2013 以降が必要)    |はい    |
|Microsoft Outlook の [差出人]、[宛先] および [Cc] フィールドのプレゼンス状態    |はい    |可    |可    |
|状態メニューから IM または通話で返信    |○ (連絡先カードから)    |○ (連絡先カードから)    |○ (連絡先カードから)    |
|[スケジュール アシスタント] タブの会議出席依頼のプレゼンス状態    |はい    |はい    |いいえ    |
|受信した電子メール メッセージのツール バーまたはリボンから、IM または電話で返信    |はい    |可    |可    |
|**その他の Office アプリケーション**   ||||
|OneNote 共有メモ    |いいえ    |あり    |いいえ    |
|Office のセットアップ プログラムに統合されたセットアップ    |不可    |あり    |いいえ    |
|PowerPoint プレゼンテーションのコンテンツ    |はい    |[はい] (VBSS も使用可能)    |○    |
|Microsoft Word および Microsoft Excel ファイルの IM およびプレゼンス表示 (スマート タグが有効)    |Microsoft Word のみ    |Microsoft Word のみ    |×    |
|Microsoft SharePoint サイトの IM およびプレゼンス (Outlook のインストールが必要)    |はい    |はい    |いいえ    |
   
& #x 2776。-をインストールし、Mac クライアントまたは Mac クライアント用の Lync 2011 で、Skype のビジネスを現在実行中のものとします。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server およびビジネス用の Skype

次の表は、Exchange Server のさまざまなバージョンのビジネスをサポートするため、Skype をについて説明します。 Extended MAPI 通話を処理するには、クライアント コンピューターに Outlook をインストールしておく必要があり、一部の機能には Exchange Web サービス (EWS) が必要です。
  
**Skype ビジネスおよび Exchange Server の互換性**

|**Exchange Server のバージョン**|**Skype ビジネスをサポートするため**|
|:-----|:-----|
|Exchange Server 2019 (Skype ビジネス サーバー 2019 のみ) |Exchange Server 2013 のサポートと同様    |
|Exchange Server 2016    |Exchange Server 2013 のサポートと同様  <br/> |
|Exchange Server 2013  <br/> |Exchange Server 2010 のサポートと同様で、次の機能を含みます。   <br/>&bull;&nbsp;&nbsp;統合連絡先ストア  <br/>&bull;&nbsp;&nbsp;高解像度の画像  <br/>&bull;&nbsp;&nbsp;アーカイブの統合  <br/> **注:** 詳細については、 [Exchange Server でサーバーをビジネス用の Skype の統合](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)を参照してください。  <br/> |
|Exchange Server 2010  <br/>(Skype ビジネス サーバー 2015 のみ) |次の機能は、EWS を通してのみ使用できます。  <br/>&bull;&nbsp;&nbsp;読み取りまたは会話の履歴フォルダー内のアイテムの削除  <br/>&bull;&nbsp;&nbsp;読み取りまたはボイス メール アイテムの削除  <br/>&bull;&nbsp;&nbsp;空き時間情報を拡張し、会議の件名と場所を表示します。  <br/>&bull;&nbsp;&nbsp;Exchange の連絡先の同期  <br/> Exchange Server 2010 で、パブリック フォルダーはオプションです。  <br/> |
   
## <a name="see-also"></a>関連項目
 
[Windows クライアントの要件およびソフトウェア サポート](windows-requirements.md)
  
[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)

