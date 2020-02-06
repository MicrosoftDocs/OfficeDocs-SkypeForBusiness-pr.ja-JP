---
title: CDR ビューのリスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: ビューは、CDR データベースからデータを返すために使用される最も一般的なシナリオに関する情報に簡単にアクセスできます。 実際の CDR データベーステーブルを使う代わりに、ビューを使ってカスタムレポートを作成することをお勧めします。これは、データベースビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
ms.openlocfilehash: 78bf18fe51cea8937de44c72b39f7c1b81c75544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815125"
---
# <a name="list-of-cdr-views"></a>CDR ビューのリスト
 
ビューは、CDR データベースからデータを返すために使用される最も一般的なシナリオに関する情報に簡単にアクセスできます。 実際の CDR データベーステーブルを使う代わりに、ビューを使ってカスタムレポートを作成することをお勧めします。これは、データベースビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
  
|**ビュー名**|**説明**|
|:-----|:-----|
|[ClientVersions ビュー](clientversions-0.md) <br/> |通信セッションで使用されているクライアントソフトウェア/デバイスについての情報を返します。  <br/> |
|[ConferenceMessageCount ビュー](conferencemessagecount-0.md) <br/> |電話会議のユーザーから送信されたメッセージの数に関する情報を返します。  <br/> |
|[会議ビュー](conferences-0.md) <br/> |開始時刻、終了時刻、会議開催者などの会議情報を返します。  <br/> |
|[ConferenceSessionDetails ビュー](conferencesessiondetails.md) <br/> |開始時刻、終了時刻、ユーザー Id、応答コード、診断 Id など、すべての会議セッションのセッションの詳細を返します。  <br/> |
|[ConferenceUris ビュー](conferenceuris-0.md) <br/> |会議で使用されている会議の Uri に関する情報を返します。  <br/> |
|[ErrorReport ビュー](errorreport-0.md) <br/> |セッション中に発生したエラーに関する情報を返します。  <br/> |
|[FileTransfers ビュー](filetransfers.md) <br/> |ファイルの名前、転送が承諾、拒否、またはキャンセルされたかどうかなど、ファイル転送セッションに関する情報を返します。  <br/> |
|[FocusJoinsAndLeaves ビュー](focusjoinsandleaves-0.md) <br/> |会議への参加と退席中のアクティビティに関する情報を返します。  <br/> |
|[McuJoinsAndLeaves ビュー](mcujoinsandleaves-0.md) <br/> |会議への参加と休暇のアクティビティについての結合された情報を返します (各会議参加は、対応する会議の退出とペアリングされています)。  <br/> |
|[Mcu ビュー](mcus-0.md) <br/> |会議サーバーに関する情報を返します。  <br/> |
|[メディアビュー](media-0.md) <br/> |ピアツーピア通信セッションで使用されているメディアの種類についての情報を返します。  <br/> |
|[進捗状況レポートビュー](progressreport-0.md) <br/> |完了したセッションに関する情報を返します。  <br/> |
|[登録表示](registration-0.md) <br/> |Skype for Business Server 2015 での登録に関する情報を返します。  <br/> |
|[セッションの詳細ビュー](sessiondetails-0.md) <br/> |VoIP 電話、2パーティの IM セッション、またはピアツーピア通信セッションなど、ピアツーピアセッションに関する情報を返します。  <br/> |
|[ユーザービュー](user.md) <br/> |コミュニケーションセッションに参加したユーザーに関する情報を返します。  <br/> |
|[VoIPDetails ビュー](voipdetails.md) <br/> |1つ以上の VoIP (ボイスオーバー IO) ユーザーを含むピアツーピアセッションの情報を返します。  <br/> |
   

