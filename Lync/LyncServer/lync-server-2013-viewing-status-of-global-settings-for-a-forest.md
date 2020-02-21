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
ms.openlocfilehash: ab574067b05b494601e0dd769003cb01904c52bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Lync Server 2013 のフォレストのグローバル設定の状態を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-20_

管理者は、Lync Server 2013 展開のグローバル設定を毎月確認する必要があります。 目的は、一連の既知の構成に対して実装済みの設定を確認することです。基準構成は、設定が有効であることを保証し、ベースラインのドキュメントを更新する必要があるかどうかを判断するためのものです。 グローバル設定の変更は、新しい設定を文書化することを含める必要がある変更管理プロセスによって実装する必要があります。

次のセクションでは、確認が必要なグローバル設定について説明します。

<div>

## <a name="check-general-settings"></a>全般設定を確認する

Lync Server 2013 でサポートされているセッション開始プロトコル (SIP) ドメインなど、全般設定を確認します。

SIP ドメイン情報は、Windows PowerShell と**new-cssipdomain**コマンドレットを使用して取得できます。 この情報を取得するには`Get-CsSipDomain` 、Windows PowerShell コマンドを実行します。

New-cssipdomain は、認証されたすべての SIP ドメインについて次のような情報を返します。

Id 名 IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com True

na.fabrikam.com na.fabrikam.com False

IsDefault プロパティが True に設定されている場合、対応するドメインが既定の SIP ドメインになります。 New-cssipdomain コマンドレットを使用して、組織の既定の SIP ドメインを変更できます。 ただし、既定の SIP ドメインを削除するだけで、既定のドメインがなくなるため、単純に削除することはできません。 前の例で示したように、fabrikam.com ドメインを削除するには、まず、既定のドメインとして na.fabrikam.com を構成する必要があります。

</div>

<div>

## <a name="check-meeting-settings"></a>会議の設定を確認する

会議の設定には、会議ポリシーの定義と、会議への匿名ユーザーの参加のサポートが含まれます。

会議の構成設定を取得するには、Windows PowerShell および**get-help/csconfiguration**コマンドレットを使用します。 たとえば、次のコマンドを実行すると、グローバルな会議の構成設定に関する情報が戻されます。

Get-help-Csconfiguration-Id "Global" 会議の構成設定をサイトスコープで構成することもできます。 そのため、次のコマンドを使用すると、すべての会議構成設定に関する情報が返されます。

`Get-CsMeetingConfiguration`

このコマンドレットを実行すると、次のような情報が**表示**されます。

Identity: Global

PstnCallersBypassLobby: True

EnableAssignedConferenceType: True

DesignateAsPresenter: Company

AssignedConferenceTypeByDefault: True

AdmitAnonymousUsersByDefault: True

この場合も、 **AdmitAnonymousUsersByDefault**の最後の項目は、匿名ユーザーが会議に参加する機能を有効または無効にします。

会議の構成設定を確認するときは、現在の設定を既定の対応物と比較すると便利な場合があります。 既定の会議構成設定を表示するには、次のコマンドを実行します。

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

前のコマンドを実行すると、グローバルな会議の構成設定のメモリ内インスタンスが作成されます。これは、各プロパティの既定値を使用するインスタンスです。 コマンドの実行時に実際の会議構成設定は作成されません。 ただし、すべての既定のプロパティの値は画面に表示されます。

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>エッジサーバーとその設定を確認する

エッジサーバーの情報は、Windows PowerShell を使用して取得できます。 このコマンドは、組織で使用するように構成されているすべてのエッジサーバーに関する情報を戻します。

`Get-CsService -EdgeServer`

返される情報には、各エッジサーバーの FQDN とポートの設定がすべて含まれています。

Identity: EdgeServer: dc.fabrikam.com

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

フェデレーション設定を確認します (構成されているかどうか、応答が "yes" の場合は FQDN とポート)。 アクセスエッジ構成設定のグローバルコレクションを使用して、フェデレーションを有効または無効にします。 特に、次のような意味では、フェデレーションが完全にまたは何もありません。組織全体に対してフェデレーションが有効になっているか、組織全体でフェデレーションが無効になっています。

アクセスエッジの構成設定は、Windows PowerShell を使用して返すことができます。 そのためには、次の Windows PowerShell コマンドを実行します。

`Get-CsAccessEdgeConfiguration`

その後、コマンドは次のようなデータを返します。

Identity: Global

AllowAnonymousUsers: False

AllowFederatedUsers: False

AllowOutsideUsers: False

BeClearingHouse: False

EnablePartnerDiscovery: False

EnableArchivingDisclaimer: False

KeepCrlsUpToDateForPeers: True

MarkSourceVerifiableOnOutgoingMessages: True

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: Usednssrvrouting は、

**AllowFederatedUsers**プロパティが True に設定されている場合は、フェデレーションが組織で有効になっていることを意味します。 ( **AllowFederatedUsers**を True に設定することも、分割ドメインのシナリオでは、オンプレミスのユーザーがクラウド内のユーザーとシームレスに通信できることを意味します)。

エッジサーバーの FQDN およびポート設定を取得するには、前のタスク (エッジサーバーとその設定) を参照してください。

グローバルスコープでフェデレーションを有効にすることは、ユーザーがフェデレーションユーザーと通信できる可能性があることを意味します。 個々のユーザーがフェデレーションユーザーと実際に通信できるかどうかを判断するには、そのユーザーに割り当てられた外部ユーザーアクセスポリシーを調査する必要があります。

外部ユーザーアクセス情報は、Windows PowerShell を使用して返すことができます。 たとえば、次のコマンドを実行すると、グローバル外部ユーザーアクセスポリシーの情報が戻されます。

`Get-CsExternalAccessPolicy -Identity "Global"`

このコマンドは、すべての外部ユーザーアクセスポリシーに関する情報を返します。

`Get-CsExternalAccessPolicy`

返される情報は次のようになります。

Identity: False

Description

EnableFederationAccess: False

EnablePublicCloudAccess: False

EnablePublicCloudAccessAudioVideoAccess: False

EnableOutsideAccess: False

**EnableFederationAccess**が True に設定されている場合、特定のポリシーによって管理されるユーザーは、フェデレーションユーザーと通信できます。

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>アーカイブ設定を確認する

内部およびフェデレーション通信のアーカイブ設定を確認します。内部および外部アーカイブの設定を確認する前に、アーカイブが有効になっていることを確認する必要があります。

アーカイブ構成設定は、Windows PowerShell と Set-csarchivingconfiguration コマンドレットを使用して確認できます。

`Get-CsArchivingConfiguration -Identity "Global"`

アーカイブ設定は、サイトスコープで構成することもできます。 すべてのアーカイブ設定に関する情報を戻すには、次のコマンドを使用します。

`Get-CsArchivingConfiguration`

Set-csarchivingconfiguration コマンドレットは、次のようなデータを返します。

Identity: Global

EnableArchiving: False

EnablePurging: False

PurgeExportedArchivesOnly: False

Blockonアーカイブエラー: False

KeepArchivingDataForDays:14

で purgehourofday: 2

ArchiveDuplicateMessages: True

CachePurgingInterval:24

EnableArchiving プロパティが False に設定されている場合は、通信セッションがアーカイブされないことを意味します。 インスタントメッセージングセッションのみをアーカイブする場合は、次のようなコマンドを使用して IM セッションのアーカイブを有効にします。

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

会議セッションおよびインスタントメッセージングセッションをアーカイブするには、次のコマンドを使用します。

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

現在のアーカイブ設定と既定の設定を比較したい場合は、次の Windows PowerShell コマンドを実行します。

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

このコマンドは、グローバルアーカイブ構成設定のメモリ内インスタンスを作成します。 これは、Lync Server で使用される設定の実際のコレクションではありません。 ただし、すべてのアーカイブ構成プロパティの既定値が表示されます。

また、次のコマンドを使用して、アーカイブサーバーの FQDN を返すこともできます。

`Get-CsService -ArchivingServer`

アーカイブが有効になっていることを確認したら、アーカイブポリシーを表示して、内部通信セッションと外部通信セッションがアーカイブされているかどうかを判断できます。

アーカイブポリシー情報は、Grant-csarchivingpolicy コマンドレットを使用して取得できます。 たとえば、次のコマンドを実行すると、グローバルアーカイブポリシーに関する情報が戻されます。

`Get-CsArchivingPolicy -Identity "Global"`

アーカイブポリシーは、サイトとユーザーごとのスコープで構成することもできます。また、このコマンドを使用して、すべてのアーカイブポリシーに関する情報を返すこともできます。

`Get-CsArchivingPolicy`

Grant-csarchivingpolicy から受け取る情報は、次のようになります。

Identity: Global

Description

アーカイブ内部: False

アーカイブ外部: False

既定では、アーカイブポリシーで内部と外部の両方のアーカイブが無効になっていることに注意してください。

</div>

<div>

## <a name="check-cdr-settings"></a>CDR の設定を確認する

ピアツーピア、電話会議、音声通話詳細記録の通話詳細記録 (CDR) 設定を確認します。 CDR の設定の詳細については、Set-cscdrconfiguration コマンドレットを使用して**取得**できます。 たとえば、次のコマンドを実行すると、CDR 構成設定のグローバルコレクションに関する情報が戻されます。

`Get-CsCdrConfiguration -Identity "Global"`

また、CDR をサイトスコープで構成することもできるので、次のコマンドを実行することもできます。このコマンドは、すべての CDR 構成設定に関する情報を返します。

`Get-CsCdrConfiguration`

Set-cscdrconfiguration コマンドレットは、CDR 構成設定のコレクションごとに、次のような情報を返します。

Identity: Global

EnableCDR: True

EnablePurging: True

KeepCallDetailForDays:60

KeepErrorReportForDays:60

で purgehourofday: 2

QoE 監視についても同様の情報を返すことができます。そのためには、このコマンドレットを使用します。 たとえば、次のコマンドを実行すると、QoE 構成設定のグローバルコレクションに関する情報が戻されます。

`Get-QoEConfiguration -Identity "Global"`

この情報は次のようになります。

Identity: Global

ExternalConsumerIssuedCertId :

EnablePurging: True

KeepQoEDataForDays:60

で purgehourofday: 1

EnableExternalConsumer: False

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: True

現在の CDR 設定を既定の CDR 設定と比較する場合は、次のコマンドを実行すると、既定値を確認できます。

`New-CsCdrConfiguration -Identity "Global" -InMemory`

同様に、QoE 監視の既定値は、次のコマンドを使用して取得できます。

`New-CsQoEConfiguration -Identity "Global" -InMemory`

また、次のコマンドを実行して、監視サーバーの FQDN を返すこともできます。

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>音声設定の確認

通常、管理者にとって重要な音声設定は、音声ポリシーと音声ルートに含まれています。音声ポリシーには、個々のユーザーに公開する機能 (通話の転送や転送など) を決定する設定が含まれています。音声ルートは、(および if) 通話が PSTN を介してルーティングされる方法を決定します。

音声ポリシー情報は、Windows PowerShell を使用して取得できます。 たとえば、次のコマンドを実行すると、グローバル音声ポリシーに関する情報が戻されます。

`Get-CsVoicePolicy -Identity "Global"`

このコマンドを実行すると、組織で使用するように構成されているすべての音声ポリシーに関する情報が戻されます。

`Get-CsVoicePolicy`

Set-csvoicepolicy コマンドレットによって返される情報は、次のようになります。

Identity: Global

PstnUsages{}

Description

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

音声ポリシーのサブセットを返すクエリを作成することもできます。 たとえば、次のコマンドは、着信転送が許可されているすべての音声ポリシーを返します。

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

このコマンドは、着信転送が許可されていないすべての音声ポリシーを返します。

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

Windows PowerShell では、CsVoiceRouting コマンドレットを使用して、音声ルートに関する情報を取得します。

`Get-CsVoiceRoute`

このコマンドは、すべての音声ルートについて次のような情報を返します。

Identity: LocalRoute

優先度: 0

Description

数字パターン: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages{}

PstnGatewayList{}

Name: LocalRoute

SuppressCallerId

AlternateCallerId

Lync Server を使用すると、PSTN を使用しない音声ルートを作成し、PSTN ゲートウェイを指定することはできません。 ただし、この2つのプロパティ値が構成されていない音声ルート経由で実際に通話をルーティングすることはできません。 そのため、このコマンドを定期的に実行することが有益な場合があります。このコマンドは、PSTN を使用していないボイスルートの id を返します。

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

同様に、次のコマンドは、PSTN ゲートウェイを持たないように構成されていないすべての音声ルートの id を返します。

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>電話会議アテンダントの設定を確認する

PSTN ダイヤルイン会議の会議アテンダント設定を確認します。 電話会議アテンダントの設定は、 **set-csdialinconferencingconfiguration**コマンドレットを使用してのみ取得できます。 これらの設定は、Lync Server コントロールパネルでは使用できません。 会議アテンダントの設定を表示するには、次のような Windows PowerShell コマンドを使用します。これは、会議アテンダント設定のグローバルコレクションを返します。

`Get-CsDialInConferencingConfiguration -Identity "Global"`

会議アテンダントの設定は、サイトスコープで構成することもできます。 会議アテンダントのすべての設定に関する情報を戻すには、代わりに次のコマンドを使用します。

`Get-CsDialInConferencingConfiguration`

Set-csdialinconferencingconfiguration コマンドレットは、次のようなデータを返します。

Identity: Global

Entryexitアナウンス ementstype: usentry

EnableNameRecording: True

EntryExitAnnouncementsEnabledByDefault: False

EntryExitAnnouncementsEnabledByDefault が False に設定されている場合、会議アナウンスは無効になります。 Entry と exit アナウンスを有効にするには、次のような Windows PowerShell コマンドを実行します。

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>関連項目


[New-cssipdomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[-Cs会議構成の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[取得-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Set-csaccessedgeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[取得-CsQoEConfiguration 場合](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-csvoiceroute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Set-csdialinconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

