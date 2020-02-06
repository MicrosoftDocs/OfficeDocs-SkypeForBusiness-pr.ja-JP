---
title: Skype for Business Server の UCWA イベント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: '概要: Skype for Business Server のユニファイドコミュニケーション Web API (UCWA) について説明します。'
ms.openlocfilehash: db6aee15564fe9fca05c33ec5a6dd37988195956
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817626"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Skype for Business Server の UCWA イベント
 
**概要:** Skype for Business Server のユニファイドコミュニケーション Web API (UCWA) について説明します。
  
Skype for Business Server では、Microsoft Exchange への連絡先検索のアクセスからモバイルクライアントのプレゼンスの更新まで、さまざまな目的で、統合コミュニケーション Web API (UCWA) を使用しています。
  
UCWA は、実行動作の記録を、"情報"、"警告"、および "エラー" のイベントの種類として書き込みます。次の表に、UCWA コンポーネントによって書き込まれる可能性があるイベントを示します。
  
|**イベント ID**|**イベントの種類**|**概要**|**原因および解決策**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |情報  <br/> |UCWA が初期化されました  <br/> |該当なし  <br/> 該当なし  <br/> |
|20002  <br/> |エラー  <br/> |初期化中に UCWA で予期しない例外が発生しました  <br/> |初期化中に予期しないエラーが発生しました  <br/> 関連付けられたイベント ログ エントリで例外の詳細を調査し、可能性のある原因を特定します  <br/> |
|20003  <br/> |エラー  <br/> |UCWA で処理不能な例外が発生しました  <br/> |処理不能な例外が発生しました  <br/> サーバーを再起動します。問題が解決しない場合は、製品サポートに問い合わせてください。  <br/> |
|20004  <br/> |エラー  <br/> |Exchange の HD 写真にアクセスできません  <br/> |Exchange への接続を利用できません  <br/> Exchange への接続が利用できることを確認します  <br/> |
|20005  <br/> |情報  <br/> |Exchange の HD 写真にアクセスできないエラーから復旧しました  <br/> |該当なし  <br/> |
|20006  <br/> |エラー  <br/> |Exchange の連絡先検索にアクセスできません  <br/> |Exchange への接続を利用できません  <br/> Exchange への接続が利用できることを確認します  <br/> |
|20007  <br/> |情報  <br/> |Exchange の連絡先を検索できないエラーから復旧しました  <br/> |該当なし  <br/> |
|20008  <br/> |警告  <br/> |アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました  <br/> |アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました  <br/> クライアントに不要なサブスクリプションがないかどうかを確認します  <br/> |
|20009  <br/> |警告  <br/> |バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました  <br/> |バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました  <br/> クライアントに不要なサブスクリプションがないかどうかを確認します  <br/> |
|20010  <br/> |エラー  <br/> |インバンド データを取得できません  <br/> |インバンド データを取得できません  <br/> 問題が解決しない場合は、製品サポートに問い合わせてください。  <br/> |
|20011  <br/> |エラー  <br/> |プレゼンスを登録できません  <br/> |プレゼンスを登録できません  <br/> 問題が解決しない場合は、製品サポートに問い合わせてください。  <br/> |
|20012  <br/> |エラー  <br/> |エンドポイントの登録に失敗しました  <br/> |エンドポイントの登録に失敗しました  <br/> 問題が解決しない場合は、製品サポートに問い合わせてください。  <br/> |
|20013  <br/> |エラー  <br/> |IM MCU を利用できません  <br/> |IM MCU を利用できません  <br/> IM MCU が実行されているかどうかを確認します  <br/> |
|20014  <br/> |情報  <br/> |IM MCU に接続できないエラーから復旧しました  <br/> |該当なし  <br/> |
|20015  <br/> |エラー  <br/> |AV MCU を利用できません  <br/> |AV MCU を利用できません  <br/> AV MCU が実行されているかどうかを確認します  <br/> |
|20016  <br/> |情報  <br/> |AV MCU に接続できないエラーから復旧しました  <br/> |該当なし  <br/> |
|20017  <br/> |エラー  <br/> |AS MCU を利用できません  <br/> |AS MCU を利用できません  <br/> AS MCU が実行されているかどうかを確認します  <br/> |
|20018  <br/> |情報  <br/> |AS MCU に接続できないエラーから復旧しました  <br/> |該当なし  <br/> |
|20019  <br/> |エラー  <br/> |データ MCU を利用できません  <br/> |データ MCU を利用できません  <br/> データ MCU が実行されていることを確認します  <br/> |
|20020  <br/> |情報  <br/> |データ MCU に接続できないエラーから復旧しました  <br/> |該当なし  <br/> |
|20021  <br/> |エラー  <br/> |IM MCU に参加できません  <br/> |IM MCU に参加できません  <br/> IM MCU が実行されているかどうかを確認します  <br/> |
|20022  <br/> |エラー  <br/> |AV MCU に参加できません  <br/> |AV MCU に参加できません  <br/> AV MCU が実行されているかどうかを確認します  <br/> |
|20023  <br/> |エラー  <br/> |AS MCU に参加できません  <br/> |AS MCU に参加できません  <br/> AS MCU が実行されているかどうかを確認します  <br/> |
|20024  <br/> |エラー  <br/> |データ MCU に参加できません  <br/> |データ MCU に参加できません  <br/> データ MCU が実行されていることを確認します  <br/> |
|20025  <br/> |エラー  <br/> |Active Directory の写真にアクセスできません  <br/> |Active Directory への接続を利用できません  <br/> Active Directory への接続が利用できることを確認します  <br/> |
|20026  <br/> |情報  <br/> |Active Directory の写真にアクセスできないエラーから復旧しました  <br/> |該当なし  <br/> |
|20027  <br/> |警告  <br/> |逆シリアル化できません  <br/> |逆シリアル化できません  <br/> 問題が解決しない場合は、製品サポートに問い合わせてください。  <br/> |
   

