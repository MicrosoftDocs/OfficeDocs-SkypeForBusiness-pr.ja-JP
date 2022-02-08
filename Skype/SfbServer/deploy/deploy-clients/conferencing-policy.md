---
title: ルーム システム アカウントSkype会議ポリシー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: このトピックでは、ルーム システム アカウントに会議ポリシーを割り当てるSkype説明します。
ms.openlocfilehash: 2bbe7f9ca07e8c17aaf0c03693fbeca7eede2457
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394399"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>ルーム システム アカウントSkype会議ポリシー
 
このトピックでは、ルーム システム アカウントに会議ポリシーを割り当てるSkype説明します。
  
## <a name="conferencing-policy-features"></a>会議ポリシーの機能

ルーム システム アカウントに割り当Skype会議ポリシーには、特定の特性が必要です。 ほとんどの場合、会議室システム クライアントSkypeスケジュールされた会議に参加するため、会議開催者の会議ポリシーは会議に影響します。 ただし、Skype for Business Serverの機能は、参加者の構成によって異なります。 たとえば、参加者のポリシーで最大 1080p のビデオ解像度が許可されている場合、開催者のポリシーで許可しない場合でも、参加者は会議でこの高解像度ビデオ機能を体験します。 次の表では、組織内の Room System アカウントの会議ポリシーを設定するときに注意する必要があるSkype設定について説明します。 
  
|機能  <br/> |値  <br/> |Comment  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |ルーム システムオーディオのSkypeする必要があります  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |[ルーム システム] Skypeの Meet Now (アドホック) ホワイトボード セッションで機能するには、Skypeする必要があります。  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |ルーム Skype、複数のビデオ ストリームをレンダリングできます  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |アカウントが有効になっているかどうかによって異エンタープライズ VoIP (「Skypeのルーム システム アカウントを有効にする」セクションSkype for Business参照)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |アカウントが有効になっている (EV) エンタープライズ VoIPによって異なります。  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |Meet Now (アドホック) 会議の N/A ですが、Skypeルーム システムはルームの前面の画面でポーリングに応答できます  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |Meet Now (アドホック) 会議の N/A ですが、Skypeルーム システムはルームの前面の画面でポーリングに応答できます  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A for Skype ルーム システム。 TRUE の場合、リモート パーティはレコードを記録できます。  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A for Skype ルーム システム。 TRUE の場合、リモート パーティはレコードを記録できます。  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |該当なし  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |該当なし  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |ルーム システム Skypeピアツーピア ビデオ セッションへの参加を有効にする  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |該当なし  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |ユーザーがSkype for Business Server、Skypeシステムは HD1080 を使用します  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Meet Now (アドホック) ホワイトボード セッション (Skypeルーム システム) に影響する  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |表の最後にメモを表示する\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |これは、許可される最大送信ビデオ ビット レートです。 Skypeシステムは、このビット レートで 1 つの 1080 ストリームを pano (RoundTable を使用する場合) と共に送信できます。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |表の最後にメモを表示する\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |該当なし  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |これを可能な限り高く設定することをお勧めします。 有効な帯域幅は、会議時のネットワーク状態によって異なります。\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |マルチビュー ビデオ ストリームをSkypeするには、ルーム システムで TRUE を指定する必要があります。  <br/> |
   
* 帯域幅計画の詳細については、「メディア トラフィックの [ネットワーク帯域幅要件」を参照してください](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)。
  
> [!NOTE]
> Skype Room System クライアントが、Lync Server 2010 プールに参加しているユーザーが主催するスケジュールされた会議に参加しようとすると、会議の開催者の会議ポリシーによって、Skype Room System クライアントがコラボレーションを実行できません。 
  
## <a name="meeting-authentication"></a>会議認証

Skype会議室システムは、制限付き会議に参加するために会議参加リンクを使用するときに、ユーザーに認証を求めるメッセージを表示します。たとえば、Outlook で会議ロビー オプションが構成されている会議などです。 この設定は、カスタマイズされた会議に対して常にオンであり、ユーザーは常にプロンプトが表示されます。 ただし、無制限の会議の場合、ユーザーは認証なしで会議に参加できます。 
  
次のコマンドを使用すると、管理者は無制限の会議を含むすべての会議に対して認証を要求できます。 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

既定では、RequireRoomSystemsAuthorization は FALSE です。 
  

