---
title: Skype Room System アカウントの会議ポリシー
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: このトピックでは、Skype Room System アカウントに会議ポリシーを割り当てる方法について説明します。
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812727"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype Room System アカウントの会議ポリシー
 
このトピックでは、Skype Room System アカウントに会議ポリシーを割り当てる方法について説明します。
  
## <a name="conferencing-policy-features"></a>会議ポリシー機能

Skype Room System アカウントに割り当てられる会議ポリシーには、特定の特性が必要です。 ほとんどの場合、Skype Room System クライアントはスケジュールされた会議に参加するため、会議の開催者の会議ポリシーは会議に影響します。 ただし、Skype for Business Server では、特定の機能は参加者の構成によって異なります。 たとえば、参加者のポリシーで最大ビデオ解像度 1080p が許可されている場合、開催者のポリシーで許可されなくても、参加者は会議でこの高解像度のビデオ機能を使用できます。 次の表では、組織内の Skype Room System アカウントの会議ポリシーを設定する際に注意する必要があるいくつかの設定について説明します。 
  
|機能  <br/> |値  <br/> |コメント  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Skype Room System オーディオの場合は true である必要があります  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Skype Room System の今すぐ会議 (アドホック) ホワイトボード セッションで Skype Room System オーディオが機能するには、true である必要があります。  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Skype Room System でマルチビューの複数のビデオ ストリームをレンダリングできます。  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |アカウントが有効になっているかどうかによって異エンタープライズ VoIP (Skype for Business の Skype Room System アカウントの有効化に関するセクションを参照)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |アカウントが有効になっているエンタープライズ VoIP (EV) によって異なります。  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |今すぐミーティング (臨時) 会議の N/A が、Skype Room System はルームの前面にある画面のポーリングに応答できます  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |今すぐミーティング (臨時) 会議の N/A が、Skype Room System はルームの前面にある画面のポーリングに応答できます  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |Skype Room System の場合は N/A。 TRUE の場合、リモート パーティはレコードを記録できます。  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |Skype Room System の場合は N/A。 TRUE の場合、リモート パーティはレコードを記録できます。  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Skype Room System クライアントがピアツーピア ビデオ セッションに参加できます。  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/A  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Skype for Business Server では無視され、Skype Room System では HD1080 が使用されます。  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Skype Room System で今すぐ会議 (アドホック) ホワイトボード セッションに影響を与える  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |表の最後にあるメモを参照\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |これは、許可される最大送信ビデオ ビット レートです。 Skype Room System では、このビット レートで 1 つの 1080 ストリームを pano (RoundTable を使用する場合) と共に送信できます。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |表の最後にあるメモを参照\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/A  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |可能な限り高く設定することをお勧めします。 有効な帯域幅は、会議時のネットワーク条件によって異なります。\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |複数表示のビデオ ストリームを確保するには、Skype Room System に TRUE を指定する必要があります。  <br/> |
   
* 帯域幅の計画については、「メディア トラフィックの [ネットワーク帯域幅要件」を参照してください](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)。
  
> [!NOTE]
> Skype Room System クライアントが、Lync Server 2010 プールに参加しているユーザーが開催するスケジュールされた会議に参加しようとすると、会議の開催者の会議ポリシーによって、Skype Room System クライアントによるコラボレーションの実行が妨げる可能性があります。 
  
## <a name="meeting-authentication"></a>会議認証

Skype Room System では、制限された会議に参加するために会議参加リンクを使用するときに、ユーザーに認証を求めるメッセージが表示されます。たとえば、Outlook で会議ロビー オプションが構成されている会議などです。 この設定は、カスタマイズされた会議に対して常にオンであり、ユーザーに対して常にプロンプトが表示されます。 ただし、制限のない会議の場合、ユーザーは認証なしで会議に参加できます。 
  
次のコマンドを使用すると、管理者は制限のない会議を含むすべての会議に対して認証を要求できます。 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

既定では、RequireRoomSystemsAuthorization は FALSE です。 
  

