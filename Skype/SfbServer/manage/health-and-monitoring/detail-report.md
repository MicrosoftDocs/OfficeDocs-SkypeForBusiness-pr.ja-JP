---
title: Skype for Business Server の会議詳細レポート
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
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '概要: Skype for Business Server で使用される電話会議詳細レポートについて説明します。'
ms.openlocfilehash: 245691fcb304a872942be4d5a9aabe8183b4db14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816907"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Skype for Business Server の会議詳細レポート

**概要:** Skype for Business Server で使用される電話会議詳細レポートについて説明します。

会議詳細レポートには、電話会議に参加したすべてのユーザーに関する詳細な情報が示されます。たとえば、ユーザーが会議に参加した日時、ユーザーが電話会議から退場した日時、ユーザーが電話会議に接続するときに使用したエンドポイントのユーザー エージェントなどの情報を確認できます。各電話会議におけるユーザーの役割 (発表者、参加者など) に関する情報も確認できます。おそらく最も重要なことは、会議への参加と終了が正常に行われたユーザーと正常に行われなかったユーザーを簡単に確認できることです。

## <a name="accessing-the-conference-detail-report"></a>会議詳細レポートへのアクセス

会議詳細レポートには、次のレポートからアクセスできます。

- [Call Admission Control Report](call-admission-control-report.md) (会議の詳細指標をクリック)

- [Failure List Report](failure-list-report.md) (電話会議指標をクリック)

- [User Activity Report](call-diagnostic-reports-per-user.md) (電話会議 URI 指標をクリック)

会議詳細レポートからは、診断レポート (詳細) 指標をクリックして[Diagnostic Report](diagnostic-report.md)にアクセスできます。

## <a name="filters"></a>フィルター

なし。会議詳細レポートにはフィルターを適用できません。

## <a name="metrics"></a>指標

次の表は、会議詳細レポートの [電話会議情報] セクションに提供される情報を示しています。

**電話会議情報の指標**


| **名前**                 | **説明**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| [**会議 URI**] <br/> | 電話会議に割り当てられる URI。次に例を示します。  <br/> sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4  <br/> |
| [**プールの FQDN**] <br/>      | セッションに関係するレジストラー プールまたはエッジ サーバーの完全修飾名。  <br/>                             |
| [**開始時刻**] <br/>     | 会議が開始した日時。  <br/>                                                                          |
| **Organizer** <br/>      | 会議を開催したユーザーの SIP アドレス。  <br/>                                                               |
| [**終了時刻**] <br/>       | 会議が終了した日時。  <br/>                                                                            |

次の表は、会議詳細レポートの [電話会議の参加] セクションに提供される情報を示しています。

**電話会議参加の指標**

|**名前**|**説明**|
|:-----|:-----|
|**ユーザー** <br/> |会議に参加したユーザーの SIP アドレス。  <br/> |
|**役割** <br/> |電話会議の参加者が担った役割 (発表者など)。  <br/> |
|**接続** <br/> |参加者のネットワーク接続 (一般には内部送信元または外部送信元)。  <br/> |
|[**参加時間**] <br/> |参加者が電話会議に参加した日時。  <br/> |
|[**退場時間**] <br/> |参加者が電話会議から退出した日時。  <br/> |
|[**ユーザー エージェント**] <br/> |参加者のエンドポイントによって使用されるソフトウェアの識別子。  <br/> |
|**診断レポート** <br/> |診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。  <br/> |

次の表に、電話会議詳細レポートの [電話会議モダリティ] セクションで提供される情報を示します。

**電話会議のモダリティの指標**

|**名前**|**説明**|
|:-----|:-----|
|**ユーザー** <br/> |会議に参加したユーザーの SIP アドレス。  <br/> |
|[**参加時間**] <br/> |参加者が電話会議に参加した日時。  <br/> |
|[**退場時間**] <br/> |参加者が電話会議を退場した日時。  <br/> |
|[**電話会議サーバー URI**] <br/> |電話会議で使用された電話会議サーバーの URI。  <br/> |
|**診断レポート** <br/> |診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。  <br/> |


