---
title: チームにユーザーのプレゼンスを構築します。
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rakayala
description: 情報の管理者は、チームでの存在について理解する必要があります。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7f6ef1e7c20e4cc08d021d30a7b52062f08a2ac
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "25705639"
---
# <a name="user-presence-in-teams"></a>チームにユーザーのプレゼンスを構築します。

プレゼンスは、マイクロソフトのチームで (および全体で Office 365) – のユーザーのプロファイルの一部であるし、ユーザーの現在の可用性と、組織の他のユーザーのステータスを示します。 既定では、かどうか他のユーザーは、利用可能なオンラインのチームを使用して、組織内のだれもが確認できます。

## <a name="presence-states-in-teams"></a>チームでのプレゼンス状態

チームで使用可能なユーザーのプレゼンス状態は次のとおりです。

|ユーザーの構成|アプリケーションの構成|
|:--- |:---|
| ![プレゼンスの使用](media/Presence_Available.png) 利用可能|![プレゼンスの使用](media/Presence_Available.png) 利用可能|
|| ![不在時の利用可能です](media/Presence_Available_OOF.png) Office から、使用可能です |
|  ![ビジー状態です。](media/Presence_Busy.png) ビジー状態です。 |  ![ビジー状態です。](media/Presence_Busy.png) ビジー状態です。  |
|| ![ビジー状態です。](media/Presence_Busy.png) 呼び出しで|
|| ![ビジー状態です。](media/Presence_Busy.png) 会議に参加 |
|| ![使用中の不在時](media/Presence_Busy_OOF.png) 不在時の呼び出しで|
|  ![不可します。](media/Presence_DND.png) 不可します。 ||
|| ![不可します。](media/Presence_DND.png) 表示します。|
| ![退席中](media/Presence_Away.png) 退席中| ![退席中](media/Presence_Away.png) 退席中|
|| ![離れた](media/Presence_Away.png)から最後の表示*時間*|
|![退席中](media/Presence_Away.png) 一時退席中| |
|| ![退席中](media/Presence_Away.png)  作業オフ|
|| ![オフライン](media/Presence_Offline.png) オフライン |
|| ![不明です](media/Presence_Unknown.png) 状態不明|
||![ブロック](media/Presence_Blocked.png) ブロックされました |
|| ![不在時](media/Presence_OOF.png) Office から|
|||
 
いくつかのオプションをユーザーが、現在のプレゼンス状態を手動で設定しての状態を取得する他のすべてのユーザーに反映されます。 その他のユーザーのプレゼンスの詳細情報も自動的に更新され、ユーザーの利用状況 (「使用可能」、「退席中」など)、Outlook の予定表の状態 (会議など)、またはチーム アプリケーションの状態 (呼び出し発表者)、リスト内のインデントされた状態にします。

退席中] にリセットされるが、ユーザーの現在の状態まで、15 分間アイドル状態のタイムアウトがあります。

人を突破できるユーザーを指定できます (不可の設定をオーバーライドすることをお問い合わせください)。 これらの設定は、アプリケーションで利用可能です。

## <a name="teams-is-not-skype-for-business"></a>チームは、ビジネスの Skype ではありません。

ビジネス用の Skype では、次の管理設定は、チームでは異なります。
- プレゼンスの共有が常に有効チーム、組織内のユーザーです。 (プレゼンスを表示できるユーザーを決定する) のプライバシーの設定は、チームで使用可能ではありません。
- (フェデレーション サービスを含む) すべてのユーザーと共有の存在は常にチーム内のユーザーの有効にします。 (であるかのデバイスのいずれか)、連絡先の一覧の下に表示されます**チャット > 連絡先**または**呼び出し > 連絡先**。
- クライアントが応答しないと画期的な機能は常に、チーム内のユーザーに対して有効にします。
- (不在時およびその他の予定表の情報が含まれています) の予定表の統合は、常に有効にチーム内のユーザーの Outlook と統合されている場合。
- *Last seen*または*から退席中*(ビジネス用の Skype でデュアル環境の場合) のインジケーターは常にチーム内のユーザーに対して有効です。
- チーム内のユーザーのカスタムのプレゼンス状態の設定が有効になっていません。

> [!NOTE]
> これらの設定をカスタマイズするのには、チームの管理者の機能は現在サポートされていません。