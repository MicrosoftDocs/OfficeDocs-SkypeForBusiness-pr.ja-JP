---
title: Skype Room System アカウント用の電話会議ポリシー
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: このトピックでは、Skype Room System アカウントに会議ポリシーを割り当てる方法について説明します。
ms.openlocfilehash: e235ac84b92f770ae16eec3bd99511e4beea8871
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003547"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype Room System アカウント用の電話会議ポリシー
 
このトピックでは、Skype Room System アカウントに会議ポリシーを割り当てる方法について説明します。
  
## <a name="conferencing-policy-features"></a>会議ポリシーの機能

Skype Room System アカウントに割り当てられている会議ポリシーは、特定の特性を持っている必要があります。 ほとんどの場合、Skype Room System クライアントはスケジュールされた会議に参加しているため、会議の開催者の会議ポリシーが会議に影響します。 ただし、Skype for Business Server の一部の機能は、参加者の設定によって異なります。 たとえば、参加者のポリシーが最大のビデオ解像度1080p を許可している場合、開催者のポリシーで許可されていない場合でも、参加者はこの高解像度のビデオ機能を会議で体験します。 次の表では、組織内の Skype Room System アカウントの会議ポリシーをセットアップする際に注意すべきいくつかの設定について説明します。 
  
|機能  <br/> |値  <br/> |コメント  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Skype Room System オーディオには true を指定する必要があります  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Skype room system の音声が skype room システムの [今すぐ会議] (アドホック) ホワイトボードセッションで動作するためには、true である必要があります。  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Skype Room システムで複数のビデオストリームを表示できる  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |アカウントがエンタープライズ Voip (EV) が有効になっているかどうかによって異なります (「Skype for Business の Skype Room System アカウントを有効にする」セクションを参照してください)。  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |アカウントでエンタープライズ VoIP (EV) が有効であるかにどうかに応じて異なります  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |[今すぐ会議] (臨時会議) では N/A。ただし、Skype Room System では、チャットルームの最初の画面で投票に応答できます。  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |[今すぐ会議] (臨時会議) では N/A。ただし、Skype Room System では、チャットルームの最初の画面で投票に応答できます。  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |Skype Room システムの場合は、該当なし。 True の場合、通話先で記録できます  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |Skype Room システムの場合は、該当なし。 True の場合、通話先で記録できます  <br/> |
|EnableFileTransfer: False  <br/> |True  <br/> |該当なし  <br/> |
|EnableP2PFileTransfer  <br/> |True  <br/> |該当なし  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Skype Room System クライアントがピアツーピアビデオセッションに参加できるようにします。  <br/> |
|AllowLargeMeetings  <br/> |False  <br/> |該当なし  <br/> |
|EnableDataCollaboration  <br/> |True  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Skype for Business Server によって無視されます。 Skype Room System は HD1080 を使用します。  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Skype Room System での [会議の開始] (アドホック) ホワイトボードセッションへの影響  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |表の最後にある「メモ」を参照してください。\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |許可される最大送信ビデオ ビット レートです。 Skype Room システムは、このビットレートで (会議が使用されている場合は) pano と共に 1 1080 ストリームを送信できます。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |表の最後にある「メモ」を参照してください。\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |該当なし  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |2万  <br/> |この設定はできるだけ高くすることをお勧めします。 有効帯域幅は、会議の時点でのネットワークの状態によって異なります。\*  <br/> |
|EnableMultiViewJoin  <br/> |True  <br/> |マルチビュービデオストリームを実現するには、Skype Room システムについて TRUE である必要があります  <br/> |
   
* 帯域幅の計画について詳しくは、「[メディアトラフィックのネットワーク帯域幅の要件](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)」をご覧ください。
  
> [!NOTE]
> Skype Room システムクライアントが、Lync Server 2010 プールを使っているユーザーによって開催されたスケジュールされた会議に参加しようとした場合、会議の開催者の会議ポリシーによって、Skype Room System クライアントがコラボレーションを実行できないようにすることができます。 
  
## <a name="meeting-authentication"></a>会議の認証

Skype Room System は、ユーザーが会議の参加リンクを使って制限された会議に参加するときに、認証を求めるメッセージを表示します。たとえば、Outlook で会議ロビーオプションが設定されている会議などです。 この設定は、カスタマイズされた会議用に常にオンになっており、ユーザーに常にメッセージが表示されます。 ただし、無制限の会議の場合、ユーザーは認証なしで会議に参加できます。 
  
管理者は、次のコマンドによって、制限のない会議を含めてすべての会議で認証を要求できます。 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

既定では、RequireRoomSystemsAuthorization は False です。 
  

