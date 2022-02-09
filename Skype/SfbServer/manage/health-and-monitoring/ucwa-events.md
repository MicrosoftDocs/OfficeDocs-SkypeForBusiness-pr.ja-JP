---
title: UCWA イベント (Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: '概要: ユニファイド コミュニケーション Web API (UCWA) の詳細については、Skype for Business Server。'
ms.openlocfilehash: e4f36747ec75085785aefcd323f8fd6671bbbfe8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399641"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>UCWA イベント (Skype for Business Server
 
**概要:** ユニファイド コミュニケーション Web API (UCWA) の詳細については、Skype for Business Server。
  
Skype for Business Serverは、連絡先検索のために Microsoft Exchange にアクセスする方法から、モバイル クライアントのプレゼンスを更新する目的で、ユニファイド コミュニケーション Web API (UCWA) を使用します。
  
UCWA は、操作動作のレコードをイベントの種類 Informational、Warning、および Error として書き込む。 次の表では、UCWA コンポーネントによって書き込み可能なイベントについて説明します。
  
|**イベント ID**|**イベントの種類**|**Summary**|**原因と解決方法**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |情報  <br/> |UCWA の初期化  <br/> |該当なし  <br/> 該当なし  <br/> |
|20002  <br/> |Error  <br/> |UCWA が初期化中に予期しない例外を検出しました  <br/> |初期化中に予期しないエラーが発生しました  <br/> 関連付けられたイベント ログ エントリの例外の詳細を調べて、考えられる原因を特定する  <br/> |
|20003  <br/> |Error  <br/> |UCWA で未処理の例外が発生しました  <br/> |未処理の例外が発生しました  <br/> サーバーを再起動します。 問題が解決しない場合は、製品サポートに問い合わせ  <br/> |
|20004  <br/> |Error  <br/> |HD 写真のExchangeにアクセスできない  <br/> |ユーザーへのExchangeは使用できません  <br/> サーバーへの接続が使用可能Exchange確認する  <br/> |
|20005  <br/> |情報  <br/> |HD 写真のファイルにアクセスExchange回復  <br/> |該当なし  <br/> |
|20006  <br/> |Error  <br/> |連絡先の検索Exchangeにアクセスできない  <br/> |ユーザーへのExchangeは使用できません  <br/> サーバーへの接続が使用可能Exchange確認する  <br/> |
|20007  <br/> |情報  <br/> |ユーザーの連絡先の検索に失敗したExchange  <br/> |該当なし  <br/> |
|20008  <br/> |警告  <br/> |アプリケーションごとに許可されているプレゼンス サブスクリプションを超えるサブスクリプションのサブスクライブを試みる  <br/> |アプリケーションごとに許可されているプレゼンス サブスクリプションを超えるサブスクリプションのサブスクライブを試みる  <br/> クライアントで不要なサブスクリプションを確認する  <br/> |
|20009  <br/> |警告  <br/> |バッチごとに許可されているプレゼンス サブスクリプションを超えるサブスクリプションのサブスクライブを試みる  <br/> |バッチごとに許可されているプレゼンス サブスクリプションを超えるサブスクリプションのサブスクライブを試みる  <br/> クライアントで不要なサブスクリプションを確認する  <br/> |
|20010  <br/> |Error  <br/> |インバンド データを取得できない  <br/> |インバンド データを取得できない  <br/> 問題が解決しない場合は、製品サポートに問い合わせ  <br/> |
|20011  <br/> |Error  <br/> |プレゼンスをサブスクライブできない  <br/> |プレゼンスをサブスクライブできない  <br/> 問題が解決しない場合は、製品サポートに問い合わせ  <br/> |
|20012  <br/> |Error  <br/> |エンドポイントの登録に失敗しました  <br/> |エンドポイントの登録に失敗しました  <br/> 問題が解決しない場合は、製品サポートに問い合わせ  <br/> |
|20013  <br/> |Error  <br/> |IM MCU は使用できません  <br/> |IM MCU は使用できません  <br/> IM MCU が実行されているかどうかを確認する  <br/> |
|20014  <br/> |情報  <br/> |IM MCU への接続に失敗した場合の復旧  <br/> |該当なし  <br/> |
|20015  <br/> |Error  <br/> |AV MCU は使用できません  <br/> |AV MCU は使用できません  <br/> AV MCU が実行されているかどうかを確認する  <br/> |
|20016  <br/> |情報  <br/> |AV MCU への接続に失敗した場合の復旧  <br/> |該当なし  <br/> |
|20017  <br/> |Error  <br/> |AS MCU は使用できません  <br/> |AS MCU は使用できません  <br/> AS MCU が実行されているかどうかを確認する  <br/> |
|20018  <br/> |情報  <br/> |AS MCU への接続に失敗した場合の復旧  <br/> |該当なし  <br/> |
|20019  <br/> |Error  <br/> |データ MCU は使用できません  <br/> |データ MCU は使用できません  <br/> データ MCU が実行されているかどうかを確認する  <br/> |
|20020  <br/> |情報  <br/> |データ MCU への接続に失敗した場合の復旧  <br/> |該当なし  <br/> |
|20021  <br/> |Error  <br/> |IM MCU に参加できない  <br/> |IM MCU に参加できない  <br/> IM MCU が実行されているかどうかを確認する  <br/> |
|20022  <br/> |Error  <br/> |AV MCU に参加できない  <br/> |AV MCU に参加できない  <br/> AV MCU が実行されているかどうかを確認する  <br/> |
|20023  <br/> |Error  <br/> |AS MCU に参加できない  <br/> |AS MCU に参加できない  <br/> AS MCU が実行されているかどうかを確認する  <br/> |
|20024  <br/> |Error  <br/> |データ MCU に参加できない  <br/> |データ MCU に参加できない  <br/> データ MCU が実行されているかどうかを確認する  <br/> |
|20025  <br/> |Error  <br/> |写真のアクティブ ディレクトリにアクセスできない  <br/> |アクティブ ディレクトリへの接続が使用できません  <br/> アクティブ ディレクトリへの接続が使用可能な状態を確認する  <br/> |
|20026  <br/> |情報  <br/> |写真のアクティブ ディレクトリにアクセスできなかった場合に復元された  <br/> |該当なし  <br/> |
|20027  <br/> |警告  <br/> |逆シリアル化できません  <br/> |逆シリアル化できません  <br/> 問題が解決しない場合は、製品サポートに問い合わせ  <br/> |
   

