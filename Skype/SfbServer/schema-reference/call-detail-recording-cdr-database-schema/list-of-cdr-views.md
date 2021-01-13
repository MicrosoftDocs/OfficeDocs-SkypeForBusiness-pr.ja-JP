---
title: CDR ビューのリスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: ビューを使用すると、CDR データベースからデータを返すために使用される最も一般的なシナリオについての情報に簡単にアクセスできます。 実際の CDR データベース テーブルを使用する代わりに、カスタム レポートの作成にはビューを使用してください。これは、データベース ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
ms.openlocfilehash: 0a3b40c9b31bb521075e78a1a8d46479200249d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813157"
---
# <a name="list-of-cdr-views"></a>CDR ビューのリスト
 
ビューを使用すると、CDR データベースからデータを返すために使用される最も一般的なシナリオについての情報に簡単にアクセスできます。 実際の CDR データベース テーブルを使用する代わりに、カスタム レポートの作成にはビューを使用してください。これは、データベース ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
  
|**View Name/ビュー名**|**説明**|
|:-----|:-----|
|[ClientVersions ビュー](clientversions-0.md) <br/> |通信セッションで使用されているクライアント ソフトウェアおよびデバイスについての情報を返します。  <br/> |
|[ConferenceMessageCount ビュー](conferencemessagecount-0.md) <br/> |電話会議でユーザーによって送信されたメッセージ数についての情報を返します。  <br/> |
|[[電話会議] ビュー](conferences-0.md) <br/> |開始時刻、終了時刻、電話会議の開催者などの、電話会議情報を返します。  <br/> |
|[ConferenceSessionDetails ビュー](conferencesessiondetails.md) <br/> |開始時刻、終了時刻、ユーザー ID、応答コード、診断 ID などの、すべての電話会議セッションのセッション詳細を返します。  <br/> |
|[ConferenceUris ビュー](conferenceuris-0.md) <br/> |電話会議で使用される電話会議 URI についての情報を返します。  <br/> |
|[ErrorReport ビュー](errorreport-0.md) <br/> |セッション中に発生したエラーについての情報を返します。  <br/> |
|[FileTransfers ビュー](filetransfers.md) <br/> |ファイル名、送信の状態 (受け入れ、拒否、取り消し) などの、ファイル送信セッションについての情報を返します。  <br/> |
|[FocusJoinsAndLeaves ビュー](focusjoinsandleaves-0.md) <br/> |会議の参加と退出のアクティビティについての情報を返します。  <br/> |
|[McuJoinsAndLeaves ビュー](mcujoinsandleaves-0.md) <br/> |会議の参加と退出のアクティビティを組み合わせた情報を返します (会議の参加と、対応する退出の情報を組み合わせて返します)。  <br/> |
|[Mcus ビュー](mcus-0.md) <br/> |電話会議サーバーについての情報を返します。  <br/> |
|[メディア ビュー](media-0.md) <br/> |ピアツーピアの通信セッションで使用されるメディアの種類についての情報を返します。  <br/> |
|[ProgressReport ビュー](progressreport-0.md) <br/> |完了したセッションについての情報を返します。  <br/> |
|[登録ビュー](registration-0.md) <br/> |Skype for Business Server 2015 への登録に関する情報を戻します。  <br/> |
|[SessionDetails ビュー](sessiondetails-0.md) <br/> |VoIP 間の通話、2 者間の IM セッション、その他のピアツーピア通信セッションなど、ピアツーピア セッションについての情報を返します。  <br/> |
|[ユーザー ビュー](user.md) <br/> |通信セッションに参加したユーザーについての情報を返します。  <br/> |
|[VoIPDetails ビュー](voipdetails.md) <br/> |少なくとも一方が VoIP (ボイス オーバー IP) ユーザーであるピアツーピア セッションの情報を返します。  <br/> |
   

