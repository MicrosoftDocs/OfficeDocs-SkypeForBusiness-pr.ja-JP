---
title: Skype Room System アカウント用の電話会議ポリシー
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: このトピックでは、Skype Room System アカウントに会議ポリシーを割り当てる方法について説明します。
ms.openlocfilehash: a9eb05c8e29a3db216bc74e5e016c2c6a8413a33
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973424"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype Room System アカウント用の電話会議ポリシー
 
このトピックでは、Skype Room System アカウントに会議ポリシーを割り当てる方法について説明します。
  
## <a name="conferencing-policy-features"></a>会議ポリシーの機能

Skype ルームのシステム アカウントに割り当てられている会議ポリシーは、特定の特性が必要です。 ほとんどの場合、Skype ルーム システムのクライアント、スケジュールされたミーティングに参加し、会議の開催者の会議ポリシーが、会議にどのように影響するためです。 ただし、ビジネス サーバーの Skype は、特定の機能は、参加者の構成に依存します。 たとえば、参加者のポリシーでは、1080 p の最大ビデオ解像度を許可している参加者が発生会議内で、この高解像度ビデオ機能開催者のポリシーが許可しない場合でもします。 次の表では、Skype の部屋のシステム アカウントが組織内の会議ポリシーを設定する際に注意する必要がありますこのようないくつかの設定について説明します。 
  
|機能  <br/> |値  <br/> |コメント  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |True  <br/> |Skype ルーム システムのオーディオの場合は true である必要があります。  <br/> |
|AllowIPVideo  <br/> |True  <br/> |Skype ルーム システムで即時相互 (ad hoc) のホワイト ボード セッションで動作する Skype ルーム システム オーディオの場合は true である必要があります。  <br/> |
|AllowMultiView  <br/> |True  <br/> |Skype ルーム システム、複数のビューを表示するのには複数のビデオ ストリームでは、します。  <br/> |
|AllowParticipantControl  <br/> |True  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|AllowAnnotations  <br/> |True  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|DisablePowerPointAnnotations  <br/> |False  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |True  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |False  <br/> |アカウントがエンタープライズ VoIP (EV) 有効になっている (を参照してください Skype の Skype ルーム システムの有効にするアカウントのビジネス セクション) であるかによって異なります  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |False  <br/> |アカウントでエンタープライズ VoIP (EV) が有効であるかにどうかに応じて異なります  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |True  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|AllowExternalUsersToSaveContent  <br/> |True  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|AllowExternalUserControl  <br/> |False  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |False  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|AllowPolls  <br/> |True  <br/> |即時相互 (ad hoc) の会議で「n/a」ですが、Skype 部屋のシステム、部屋の前に画面上ポーリングに応答できます。  <br/> |
|AllowSharedNotes  <br/> |True  <br/> |即時相互 (ad hoc) の会議で「n/a」ですが、Skype 部屋のシステム、部屋の前に画面上ポーリングに応答できます。  <br/> |
|EnableDialInConferencing  <br/> |True  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|AllowConferenceRecording  <br/> |False  <br/> |Skype ルーム システムの該当なし。 True の場合、通話先で記録できます  <br/> |
|EnableP2PRecording  <br/> |False  <br/> |Skype ルーム システムの該当なし。 True の場合、通話先で記録できます  <br/> |
|EnableFileTransfer  <br/> |True  <br/> |該当なし  <br/> |
|EnableP2PFileTransfer  <br/> |True  <br/> |該当なし  <br/> |
|EnableP2PVideo  <br/> |True  <br/> |Skype ルーム システム クライアントがピア ツー ピア ビデオ セッションに参加するには  <br/> |
|AllowLargeMeetings  <br/> |False  <br/> |該当なし  <br/> |
|EnableDataCollaboration  <br/> |True  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Skype ビジネス サーバーの無視、Skype ルームのシステムを使用して、HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Skype ルーム システムの相互 (ad hoc) のホワイト ボード セッションを即時に影響を与えます  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |テーブルの末尾にあるメモを参照してください。\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |許可される最大送信ビデオ ビット レートです。 Skype ルームのシステムは、いずれかを送信できる 1080 ストリーム pano と共に使用する場合円卓会議は、このビット レートで。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |テーブルの末尾にあるメモを参照してください。\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |該当なし  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |設定することこのできるだけ高くすることをお勧めします。 効果的な帯域幅は、会議の時に、ネットワークの状態に依存します。\*  <br/> |
|EnableMultiViewJoin  <br/> |True  <br/> |TRUE にする必要があります Skype ルームのシステム ビューの複数のビデオ ストリームの  <br/> |
   
* 帯域幅の計画方法の詳細については、[メディア トラフィック用のネットワーク帯域幅の要件](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)を参照してください。
  
> [!NOTE]
> Skype ルーム システムのクライアントでは、Lync Server 2010 プールのホーム サーバーがユーザーごとのスケジュールされたミーティングに参加しようとして、会議の開催者の会議ポリシー防ぐことが Skype ルーム システムのクライアント共同作業を実行します。 
  
## <a name="meeting-authentication"></a>会議の認証

Skype ルーム メッセージが表示されますユーザーに会議を使用するときは制限されているミーティングに参加する参加リンクたとえば、Outlook でどのミーティング ロビーのオプションを設定した会議です。 この設定は常に上に、カスタマイズされた会議と、ユーザーが常にメッセージが表示されます。 制限なしの会議では、ユーザーは認証なしの会議に参加できます。 
  
管理者は、次のコマンドによって、制限のない会議を含めてすべての会議で認証を要求できます。 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

既定では、RequireRoomSystemsAuthorization は False です。 
  

