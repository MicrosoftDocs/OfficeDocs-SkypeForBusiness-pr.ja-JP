---
title: Skype for Business Server の UCWA イベント
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: '概要: Skype for Business Server の Unified Communications Web API (UCWA) について説明します。'
ms.openlocfilehash: d8426418bf01954137a1bbed25d5fef93443dc5c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816667"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Skype for Business Server の UCWA イベント
 
**概要:** Skype for Business Server の Unified Communications Web API (UCWA) について説明します。
  
Skype for Business Server は、連絡先検索用の Microsoft Exchange へのアクセスからモバイル クライアントのプレゼンスの更新まで、多くの目的で Unified Communications Web API (UCWA) を使用します。
  
UCWA は、イベントの種類が情報、警告、およびエラーとして動作の記録を書き込む。 次の表では、UCWA コンポーネントによって書き込まれるイベントについて説明します。
  
|**イベント ID**|**イベントの種類**|**Summary**|**原因と解決策**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |情報提供  <br/> |UCWA が初期化されました  <br/> |N/A  <br/> N/A  <br/> |
|20002  <br/> |Error  <br/> |初期化中に UCWA で予期しない例外が発生しました  <br/> |初期化中に予期しないエラーが発生しました  <br/> 関連付けられたイベント ログ エントリの例外の詳細を調べて、考えられる原因を特定する  <br/> |
|20003  <br/> |Error  <br/> |UCWA で未処理の例外が発生しました  <br/> |未処理の例外が発生しました  <br/> サーバーを再起動します。 問題が解決しない場合は、製品サポートにお問い合わせください。  <br/> |
|20004  <br/> |Error  <br/> |Exchange for HD 写真にアクセスできない  <br/> |Exchange への接続が使用できません  <br/> Exchange への接続が使用可能なのを確認する  <br/> |
|20005  <br/> |情報提供  <br/> |Exchange for HD 写真にアクセスできなかった場合から回復しました  <br/> |N/A  <br/> |
|20006  <br/> |Error  <br/> |連絡先検索用に Exchange にアクセスできない  <br/> |Exchange への接続が使用できません  <br/> Exchange への接続が使用可能なのを確認する  <br/> |
|20007  <br/> |情報提供  <br/> |Exchange で連絡先の検索に失敗した場合から回復しました  <br/> |N/A  <br/> |
|20008  <br/> |警告  <br/> |アプリケーションごとに許可されているプレゼンス サブスクリプションを超えるサブスクリプションのサブスクライブを試みる  <br/> |アプリケーションごとに許可されているプレゼンス サブスクリプションを超えるサブスクリプションのサブスクライブを試みる  <br/> クライアントで不要なサブスクリプションを確認する  <br/> |
|20009  <br/> |警告  <br/> |バッチごとに許可されているプレゼンス サブスクリプションを超えるサブスクリプションのサブスクライブを試みる  <br/> |バッチごとに許可されているプレゼンス サブスクリプションを超えるサブスクリプションのサブスクライブを試みる  <br/> クライアントで不要なサブスクリプションを確認する  <br/> |
|20010  <br/> |Error  <br/> |インバンド データを取得できません  <br/> |インバンド データを取得できません  <br/> 問題が解決しない場合は、製品サポートにお問い合わせください。  <br/> |
|20011  <br/> |Error  <br/> |プレゼンスをサブスクライブできません  <br/> |プレゼンスをサブスクライブできません  <br/> 問題が解決しない場合は、製品サポートにお問い合わせください。  <br/> |
|20012  <br/> |Error  <br/> |エンドポイントの登録に失敗しました  <br/> |エンドポイントの登録に失敗しました  <br/> 問題が解決しない場合は、製品サポートにお問い合わせください。  <br/> |
|20013  <br/> |Error  <br/> |IM MCU は使用できません  <br/> |IM MCU は使用できません  <br/> IM MCU が実行されているかどうかを確認する  <br/> |
|20014  <br/> |情報提供  <br/> |IM MCU に接続できない状態から回復しました  <br/> |N/A  <br/> |
|20015  <br/> |Error  <br/> |AV MCU が使用できない  <br/> |AV MCU が使用できない  <br/> AV MCU が実行されているかどうかを確認する  <br/> |
|20016  <br/> |情報提供  <br/> |AV MCU に接続できない状態から回復しました  <br/> |N/A  <br/> |
|20017  <br/> |Error  <br/> |AS MCU を使用できません  <br/> |AS MCU を使用できません  <br/> AS MCU が実行されているかどうかを確認する  <br/> |
|20018  <br/> |情報提供  <br/> |AS MCU に接続できない状態から回復しました  <br/> |N/A  <br/> |
|20019  <br/> |Error  <br/> |Data MCU を使用できません  <br/> |Data MCU を使用できません  <br/> Data MCU が実行されているかどうかを確認する  <br/> |
|20020  <br/> |情報提供  <br/> |Data MCU に接続できない状態から回復しました  <br/> |N/A  <br/> |
|20021  <br/> |Error  <br/> |IM MCU に参加できません  <br/> |IM MCU に参加できません  <br/> IM MCU が実行されているかどうかを確認する  <br/> |
|20022  <br/> |Error  <br/> |AV MCU に参加できません  <br/> |AV MCU に参加できません  <br/> AV MCU が実行されているかどうかを確認する  <br/> |
|20023  <br/> |Error  <br/> |AS MCU に参加できません  <br/> |AS MCU に参加できません  <br/> AS MCU が実行されているかどうかを確認する  <br/> |
|20024  <br/> |Error  <br/> |Data MCU に参加できません  <br/> |Data MCU に参加できません  <br/> Data MCU が実行されているかどうかを確認する  <br/> |
|20025  <br/> |Error  <br/> |写真の Active Directory にアクセスできません  <br/> |Active Directory への接続が使用できません  <br/> Active Directory への接続が使用可能な状態を確認する  <br/> |
|20026  <br/> |情報提供  <br/> |写真用の Active Directory にアクセスできなかった場合から回復しました  <br/> |N/A  <br/> |
|20027  <br/> |警告  <br/> |逆シリアル化できない  <br/> |逆シリアル化できない  <br/> 問題が解決しない場合は、製品サポートにお問い合わせください。  <br/> |
   

