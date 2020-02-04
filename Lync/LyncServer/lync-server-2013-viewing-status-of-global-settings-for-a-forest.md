---
title: 'Lync Server 2013: フォレストのグローバル設定の状態を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec1dea4ad3d5052bc2ba23cccd9e19ab138414ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Lync Server 2013 でフォレストのグローバル設定の状態を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-20_

管理者は、Lync Server 2013 展開のグローバル設定を毎月確認する必要があります。 目標として、実装されている設定を既知の構成のセットと照らし合わせて確認します。設定は有効であることを保証し、ベースラインのドキュメントを更新する必要があるかどうかを判断するための基準構成となります。 グローバル設定の変更は、新しい設定の文書化を含める必要がある変更管理プロセスによって実装する必要があります。

レビューする必要があるグローバル設定については、次のセクションで説明します。

<div>

## <a name="check-general-settings"></a>全般設定を確認する

Lync Server 2013 でサポートされているセッション開始プロトコル (SIP) ドメインなど、一般的な設定を確認します。

SIP ドメイン情報は、Windows PowerShell と**CsSipDomain**コマンドレットを使って返すことができます。 この情報を返すには、 `Get-CsSipDomain` Windows PowerShell コマンドを実行します。

CsSipDomain は、認証されたすべての SIP ドメインについて、次のような情報を返します。

識別名の IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com True

na.fabrikam.com na.fabrikam.com False

IsDefault プロパティが True に設定されている場合、対応するドメインは既定の SIP ドメインになります。 CsSipDomain コマンドレットを使用して、組織の既定の SIP ドメインを変更できます。 ただし、既定のドメインがないままであるため、既定の SIP ドメインを削除することはできません。 (前の例で示したように) fabrikam.com ドメインを削除する場合は、最初に既定のドメインとなるように na.fabrikam.com を設定する必要があります。

</div>

<div>

## <a name="check-meeting-settings"></a>会議の設定を確認する

会議の設定には、会議のポリシー定義と、会議での匿名ユーザーの参加のサポートが含まれます。

会議の構成設定を取得するには、Windows PowerShell を使用するか、または**csmeeting 構成**コマンドレットを使用します。 たとえば、次のコマンドは、グローバル会議の構成設定に関する情報を返します。

Cs会議構成– Id "グローバル" 会議の構成設定は、サイトのスコープで構成することもできます。 そのため、次のコマンドを使用することができます。これは、すべての会議の構成設定に関する情報を返します。

`Get-CsMeetingConfiguration`

**Cs会議構成**コマンドレットは、次のような情報を返します。

Identity: グローバル

PstnCallersBypassLobby: True

EnableAssignedConferenceType: True

デザインの発表者: 会社

AssignedConferenceTypeByDefault: True

AdmitAnonymousUsersByDefault: True

**AdmitAnonymousUsersByDefault**の最後の項目では、匿名ユーザーが会議に参加する機能を有効または無効にします。

会議の構成設定を確認するときに、現在の設定を既定の対応する値と比較すると便利な場合があります。 次のコマンドを実行して、既定の会議構成設定を表示できます。

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

前のコマンドでは、グローバル会議構成設定のメモリ内のインスタンス (各プロパティの既定値を使用するインスタンス) が作成されます。 このコマンドを実行しても、実際の会議の構成設定は作成されません。 ただし、すべての既定のプロパティ値が画面に表示されます。

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>エッジサーバーとその設定を確認する

エッジサーバーの情報は、Windows PowerShell を使用して取得できます。 このコマンドは、組織で使用するように構成されているすべてのエッジサーバーについての情報を返します。

`Get-CsService -EdgeServer`

返される情報には、各エッジサーバーの FQDN とポートの設定がすべて含まれています。

Id: EdgeServer: dc.fabrikam.com

レジストラー: レジストラー: LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort: 5061

AccessEdgeExternalSipPort: 5061

AccessEdgeClientPort: 443

DataPsomServerPort: 8057

DataPsomClientPort: 444

MediaRelayAuthEdgePort: 5062

MediaRelayAuthInternalTurnTcpPort: 443

MediaRelayAuthExternalTurnTcpPort: 445

MediaRelayAuthInternalTurnUdpPort: 3478

MediaRelayAuthExternalTurnUdpPort: 3478

MediaCommunicationPortStart: 5万

MediaComunicationPortCount: 1万

AccessEdgeExternalFqdn: dc.fabrikam.com

DataEdgeExternalFqdn: dc.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn: dc.fabrikam.com

DependentServiceList: {レジストラー: LYNC-SE.fabrikam.com,

ConferencingServer: LYNC-SE

com、MediationServer: LYNC-SE。

fabrikam.com}

ServiceId: fabrikam.com-EdgeServer

SiteId: サイト: fabrikam

PoolFqdn: dc.fabrikam.com

バージョン: 5

役割: EdgeServer

<div>

## <a name="check-federation-settings"></a>フェデレーション設定を確認する

構成されているかどうかなど、フェデレーション設定を確認します。回答が "yes" の場合は、FQDN とポートを確認します。 フェデレーションは、アクセスエッジ構成のグローバルコレクションを使って有効または無効にします。 特に、フェデレーションがすべてまたはまったく機能していないことを意味します。組織全体でフェデレーションが有効になっているか、組織全体でフェデレーションが無効になっていることを意味します。

アクセスエッジの構成設定は、Windows PowerShell を使用して返すことができます。 そのためには、次の Windows PowerShell コマンドを実行します。

`Get-CsAccessEdgeConfiguration`

このコマンドを実行すると、次のようなデータが返されます。

Identity: グローバル

AllowAnonymousUsers: False

AllowFederatedUsers: False

AllowOutsideUsers: False

BeClearingHouse: False

EnablePartnerDiscovery: False

EnableArchivingDisclaimer: False

KeepCrlsUpToDateForPeers: True

MarkSourceVerifiableOnOutgoingMessages: True

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: UseDnsSrvRouting

**AllowFederatedUsers**プロパティが True に設定されている場合は、組織でフェデレーションが有効になっていることを意味します。 ( **AllowFederatedUsers**を True に設定すると、分割されたドメインのシナリオでは、オンプレミスのユーザーはクラウド内のユーザーとシームレスに通信できることを意味します)。

エッジサーバーの FQDN とポートの設定を取得するには、前のタスク (エッジサーバーとその設定) を参照してください。

グローバルスコープでフェデレーションを有効にすると、ユーザーはフェデレーションされたユーザーと通信できる可能性があります。 個々のユーザーが実際にフェデレーションユーザーと通信できるかどうかを判断するには、そのユーザーに割り当てられている外部ユーザーアクセスポリシーを調べる必要があります。

外部ユーザーアクセスの情報は、Windows PowerShell を使用して返すことができます。 たとえば、次のコマンドは、グローバル外部ユーザーアクセスポリシーに関する情報を返します。

`Get-CsExternalAccessPolicy -Identity "Global"`

このコマンドは、すべての外部ユーザーアクセスポリシーに関する情報を返します。

`Get-CsExternalAccessPolicy`

返される情報は次のようになります。

Id: False

説明

EnableFederationAccess: False

EnablePublicCloudAccess: False

EnablePublicCloudAccessAudioVideoAccess: False

EnableOutsideAccess: False

**EnableFederationAccess**が True に設定されている場合、特定のポリシーによって管理されるユーザーはフェデレーションユーザーと通信できます。

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>アーカイブ設定を確認する

内部およびフェデレーションされた通信のアーカイブ設定を確認します。内部および外部のアーカイブの設定を確認する前に、アーカイブが有効になっていることを確認する必要があります。

アーカイブ構成の設定を確認するには、Windows PowerShell と CsArchivingConfiguration コマンドレットを使用します。

`Get-CsArchivingConfiguration -Identity "Global"`

アーカイブ設定は、サイトのスコープで構成することもできます。 すべてのアーカイブ設定に関する情報を取得するには、次のコマンドを使用します。

`Get-CsArchivingConfiguration`

CsArchivingConfiguration コマンドレットを実行すると、次のようなデータが返されます。

Identity: グローバル

EnableArchiving: False

EnablePurging: False

PurgeExportedArchivesOnly: False

Blockonアーカイブエラー: False

KeepArchivingDataForDays:14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: True

CachePurgingInterval:24

EnableArchiving プロパティが False に設定されている場合は、通信セッションがアーカイブされないことを意味します。 インスタントメッセージングセッションのみをアーカイブする場合は、次のようなコマンドを使用して、IM セッションのアーカイブを有効にします。

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

会議セッションとインスタントメッセージングセッションをアーカイブするには、次のコマンドを使用します。

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

現在のアーカイブ設定と既定の設定を比較する場合は、次の Windows PowerShell コマンドを実行します。

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

このコマンドによって、グローバルアーカイブ構成の設定のメモリ内のみのインスタンスが作成されます。 これは、Lync Server によって使用される設定の実際のコレクションではありません。 ただし、すべてのアーカイブ構成プロパティの既定値が表示されます。

このコマンドを使用して、アーカイブサーバーの FQDN を返すこともできます。

`Get-CsService -ArchivingServer`

アーカイブが有効になっていることを確認したら、アーカイブポリシーを表示して、内部と外部の通信セッションがアーカイブされているかどうかを確認できます。

CsArchivingPolicy コマンドレットを使用して、アーカイブポリシー情報を取得できます。 たとえば、次のコマンドはグローバルアーカイブポリシーに関する情報を返します。

`Get-CsArchivingPolicy -Identity "Global"`

アーカイブポリシーは、サイトとユーザーごとのスコープで構成することもできるため、次のコマンドを使用して、すべてのアーカイブポリシーに関する情報を返すこともできます。

`Get-CsArchivingPolicy`

CsArchivingPolicy から受け取った情報は、次のようになります。

Identity: グローバル

説明

アーカイブ内部: False

アーカイブ外部: False

アーカイブポリシーでは、既定では、内部および外部のアーカイブの両方が無効になっていることに注意してください。

</div>

<div>

## <a name="check-cdr-settings"></a>CDR の設定を確認する

ピアツーピア、電話会議、音声通話の詳細記録の通話の詳細レコード (CDR) 設定を確認します。 CDR の設定の詳細については、CsCdrConfiguration コマンドレットを使用して**取得**できます。 たとえば、次のコマンドは、CDR 構成設定のグローバルコレクションに関する情報を返します。

`Get-CsCdrConfiguration -Identity "Global"`

また、CDR はサイトのスコープでも設定できるため、このコマンドを実行することもできます。これは、すべての CDR 構成の設定に関する情報を返します。

`Get-CsCdrConfiguration`

CsCdrConfiguration コマンドレットは、CDR 構成設定のコレクションごとに、次のような情報を返します。

Identity: グローバル

EnableCDR: True

EnablePurging: True

KeepCallDetailForDays:60

KeepErrorReportForDays:60

PurgeHourOfDay: 2

QoE の監視についても同様の情報を取得するには、CsQoEConfiguration 指定コマンドレットを使用します。 たとえば、次のコマンドは、QoE 構成設定のグローバルコレクションに関する情報を返します。

`Get-QoEConfiguration -Identity "Global"`

この情報は次のようになります。

Identity: グローバル

ExternalConsumerIssuedCertId :

EnablePurging: True

KeepQoEDataForDays:60

PurgeHourOfDay: 1

EnableExternalConsumer: False

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: True

現在の CDR 設定と既定の CDR 設定を比較する場合は、次のコマンドを実行して既定値を確認できます。

`New-CsCdrConfiguration -Identity "Global" -InMemory`

同様に、次のコマンドを使用して、QoE モニターの既定値を取得できます。

`New-CsQoEConfiguration -Identity "Global" -InMemory`

このコマンドを実行して、監視サーバーの FQDN を返すこともできます。

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>音声の設定を確認する

音声の設定は、通常、管理者にとって重要です。音声ポリシーには、個々のユーザーに対して公開される機能を決定する設定 (通話の転送や転送機能など) が含まれます。ボイスルートは、通話が PSTN を介してどのようにルーティングされるかを決定します。

音声ポリシー情報は、Windows PowerShell を使用して取得できます。 たとえば、次のコマンドはグローバルボイスポリシーに関する情報を返します。

`Get-CsVoicePolicy -Identity "Global"`

このコマンドは、組織で使用するように構成されているすべてのボイスポリシーに関する情報を返します。

`Get-CsVoicePolicy`

CsVoicePolicy コマンドレットによって返される情報は、次のようになります。

Identity: グローバル

PstnUsages :{}

説明

AllowSimulRing: True

AllowCallForwarding: True

AllowPSTNReRouting: True

Name: DefaultPolicy

EnableDelegation: True

EnableTeamCall: True

EnableCallTransfer: True

EnableCallPark: False

EnableMaliciousCallTracing: False

EnableBWPolicyOverride: False

PreventPSTNTollBypass: False

音声ポリシーのサブセットを返すクエリを作成することもできます。 たとえば、次のコマンドは、着信の転送を許可するすべての音声ポリシーを返します。

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

このコマンドは、着信の転送を許可していないすべての音声ポリシーを返します。

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

Windows PowerShell では、CsVoiceRouting コマンドレットを使用して、音声ルートに関する情報を取得します。

`Get-CsVoiceRoute`

このコマンドは、すべての音声ルートについて、次のような情報を返します。

Identity: LocalRoute

優先度: 0

説明

数字パターン: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages :{}

PstnGatewayList :{}

Name: LocalRoute

SuppressCallerId :

AlternateCallerId :

Lync Server を使用すると、PSTN を使わず、PSTN ゲートウェイを指定しないボイスルートを作成できます。 ただし、この2つのプロパティ値が構成されていないボイスルーティングでは、実際に着信をルーティングすることはできません。 そのため、このコマンドを定期的に実行すると便利な場合があります。これは、PSTN を使用していないボイスルートの id を返します。

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

同様に、このコマンドは、PSTN ゲートウェイを使用するように構成されていないすべてのボイスルートの id を返します。

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>会議アテンダントの設定を確認する

PSTN ダイヤルイン会議の会議アテンダントの設定を確認します。 会議アテンダントの設定を取得するには、 **CsDialInConferencingConfiguration**コマンドレットを使用します。 これらの設定は Lync Server コントロールパネルでは使用できません。 会議アテンダントの設定を表示するには、次のような Windows PowerShell コマンドを使います。これは、会議アテンダント設定のグローバルコレクションを返します。

`Get-CsDialInConferencingConfiguration -Identity "Global"`

会議アテンダントの設定は、サイトのスコープで構成することもできます。 会議アテンダントのすべての設定に関する情報を取得するには、代わりに次のコマンドを使用します。

`Get-CsDialInConferencingConfiguration`

CsDialInConferencingConfiguration コマンドレットを実行すると、次のようなデータが返されます。

Identity: グローバル

Entryexitアナウンスの場合: UseNames

EnableNameRecording: True

EntryExitAnnouncementsEnabledByDefault: False

EntryExitAnnouncementsEnabledByDefault が False に設定されている場合は、会議のアナウンスが無効になっていることを意味します。 エントリと終了のアナウンスを有効にするには、次のように Windows PowerShell コマンドを実行します。

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[CsService の入手](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[取得-CsQoEConfiguration しくみ](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

