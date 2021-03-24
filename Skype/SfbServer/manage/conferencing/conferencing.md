---
title: Skype for Business Server での会議の管理
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
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: '概要: Skype for Business Server で会議を管理する方法について説明します。'
ms.openlocfilehash: 113fe27a71057fb36534b09d5e7531a25187dd9f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099073"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Skype for Business Server での会議の管理
 
**概要:** Skype for Business Server で会議を管理する方法について説明します。
  
このトピックでは、会議を管理する方法について説明します。 会議を計画および展開する方法の詳細については [、「Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) での会議の計画」および「Skype for Business Server での会議の展開 [」を参照してください](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
Skype for Business Server では、次のように構成とポリシー設定を指定して、会議の詳細を管理します。 会議と会議という用語は、同じ意味で使用される場合があります。 ただし、一般に、会議は会議の特定のインスタンスと考える場合があります。
  
- **会議ポリシー設定には** 、会議に IP オーディオとビデオを含めるかどうかから、出席できる最大人数まで、さまざまなスケジュールと参加オプションが含まれます。 会議ポリシーを使用して、会議のセキュリティ、帯域幅、法的側面を管理できます。
    
    会議ポリシーはユーザーまたはサイトに適用され、特定の会議には適用できないことに注意してください。 そのため、会議の会議出席依頼は数週間前に作成できますが、制限付き会議ポリシーは会議の開始直前に会議開催者の Skype for Business アカウントに適用する必要があります。 
    
    会議開催者の役割に専用のアカウントを使用する場合、会議ポリシーは引き続きそのアカウントに割り当てることができます。 会議開催者が一般的な Skype for Business アカウントを使用している場合は、会議の終了後にポリシーを削除する必要があります。
    
- **会議の構成設定** は、匿名ユーザーとダイヤルイン会議ユーザーがこれらの会議に参加する方法 (または場合によっては) を制御するだけでなく、ユーザーが作成できる会議の種類を決定します。 これらの設定は、スケジュールされた会議にのみ影響を与える点に注意してください。 会議の構成は、プールごとに、サイトごとに、またはグローバルに適用されます。
    
- **会議の構成設定は** 、会議のコンテンツと資料の最大許容サイズなどの設定を決定します。アプリケーション共有会議サービスの最大帯域幅。ストレージの制限と有効期限。サポートされているクライアントの内部および外部ダウンロードの URL。ユーザーが会議のヘルプとリソースを取得できる内部および外部 URL へのポインター。アプリケーション共有、クライアント オーディオ、ファイル転送、およびメディア トラフィックに使用されるポート。
    
    これらの設定を使用すると、実際のサーバー自体を管理できます。 これらの設定は、Skype for Business Server 管理シェルを使用してのみ設定できます。 
    
- **ダイヤルイン アクセス設定を使用** すると、ユーザーが電話からダイヤルインするかどうかと方法に関する情報を定義できます。 [コントロール パネルの電話会議] タブと、ダイヤル プラン、音声ポリシー、ルート、PSTN 使用法などの一部のダイヤルイン情報 ([コントロール パネルの音声ルーティング] タブ) から、アクセス番号などの一部のダイヤルイン アクセス情報を指定します。
    
- **PIN ポリシー設定を** 使用すると、参加者がダイヤルイン アクセスに使用する PIN に名前を付け、定義できます。
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して会議を管理する

ほとんどの会議ポリシーと構成設定は、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して管理できます。 一部の構成設定は、Skype for Business Server 管理シェルを使用する場合にのみ使用できます。
  
- 会議ポリシー設定を管理するには、次の方法を使用します。
    
  - [コントロール パネル] で、[会議 **] を選択|会議ポリシー**.
    
  - PowerShell で **、-CsConferencingPolicy コマンドレットを検索** します。
    
- 会議の構成設定を管理するには、次の方法を実行します。
    
  - [コントロール パネル] で、[会議 **] を選択|会議の構成**。
    
  - Skype for Business Server 管理シェルで **、-CsMeetingConfiguration コマンドレットを** 検索します。
    
- ダイヤルイン アクセス番号の設定を管理するには、次の方法を使用します。
    
  - [コントロール パネル] で、[会議 **] を選択|ダイヤルイン アクセス番号**。
    
  - Skype for Business Server 管理シェルで **、-CsDialInConferencing コマンドレットを** 検索します。
    
- ダイヤル プラン、音声ポリシー、ルート、PSTN 使用法などのダイヤルイン アクセス情報を管理するには、次の方法を使用します。 
    
  - [コントロール パネル] で、[会議 **] を選択|音声ルーティング**。
    
  - Skype for Business Server 管理シェルで **、-CsDialPlan コマンドレット** と **-CsVoice** コマンドレットを検索します。
    
- PIN ポリシー設定を管理するには、次の方法を使用します。
    
  - [コントロール パネル] で、[会議 **] を選択|PIN ポリシー**。
    
  - Skype for Business Server 管理シェルで **、-CsPinPolicy コマンドレットを** 検索します。
    
- 会議の構成設定を管理するには、Skype for Business Server 管理シェルを使用する必要があります。 **-CsConferencingConfiguration コマンドレットを** 検索します。
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype for Business Server Management Shell コマンドレット

次の Skype for Business Server Management Shell コマンドレットを使用して会議を管理できます。 
  
**会議ポリシーの設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |組織で使用するように構成されている会議ポリシーに関する情報を返します。 会議ポリシーは、会議で使用できる機能を決定します。これには、会議に IP オーディオとビデオを含めるかどうかから、会議に出席できるユーザーの最大数までが含まれます。  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |ユーザーごとのスコープで会議ポリシーを割り当てます。  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |組織で使用する新しい会議ポリシーを作成します。  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |指定した会議ポリシーを削除します。  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |既存の会議ポリシーを変更します。  <br/> |
   
**会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用されている会議構成設定に関する情報を返します。 会議構成設定は、ユーザーが作成できる会議の種類を決定し、匿名ユーザーとダイヤルイン会議ユーザーがこれらの会議に参加する方法 (または場合によっては) を制御するのに役立ちます。  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |サイトまたはサービス スコープで会議構成設定の新しいコレクションを作成します。 これらの設定は、スケジュールされた会議にのみ影響を与える点に注意してください。Skype for Business の [今すぐ会議] オプションをクリックして作成されたアドホック会議には影響を与えかねない。  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |会議構成設定の既存のコレクションを削除します。  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用されている会議の構成設定を変更します。  <br/> |
   
**会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |組織の会議構成設定に関する情報を返します。 会議設定は、会議コンテンツや配布資料の最大許容サイズ、コンテンツの猶予期間 (コンテンツが削除されるまでに保存される期間)、サポートされているクライアントの内部および外部ダウンロード用 URL などを決定します。  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |会議の構成設定の新しいコレクションを作成します。  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |指定された会議構成設定のコレクションを削除します。  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |会議構成設定の既存のコレクションを変更します。  <br/> |
   
**ダイヤルイン構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |組織で使用するように構成された会議ディレクトリに関する情報を返します。 会議ディレクトリは、ダイヤルイン会議ユーザーが会議情報を検索するのに役立ちます。  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーがダイヤルイン会議に参加または退出するときに Skype for Business Server がどのように応答するかに関する情報を取得します。  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |組織で使用するように構成されたすべてのダイヤルイン会議アクセス番号に関する情報を戻します。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議で使用されるデュアルトーン多重周波数 (DTMF) の信号設定を戻します。 DTMF を使用すると、会議にダイヤルインするユーザーは、電話のキーパッドで会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Skype for Business Server ダイヤルイン会議で使用するためにサポートされている、地域/少数民族の言語を含む言語の一覧を返します。 これらの言語は、電話を使用して会議に出席しているユーザーにオーディオ メッセージと指示を中継するときに使用されます。  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |組織で使用されるダイヤル プランに関する情報を戻します。  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |ダイヤル プランを、1 つまたは複数のユーザーあるいはグループに割り当てます。  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |会議ディレクトリを、Microsoft Office Server 2007 R2 から Skype for Business Server にインポートします。 これにより、Skype for Business Server とコミュニケーション サーバー 2007 R2 Office相互運用性が提供されます。  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |既存の会議ディレクトリを別のプールに移動します。 会議ディレクトリは、ダイヤルイン会議ユーザーが会議情報を検索するのに役立ちます。  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |組織で使用できるように新しい会議ディレクトリを作成します。 会議ディレクトリは、ダイヤルイン会議ユーザーが会議情報を検索するのに役立ちます。  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |新しいダイヤルイン会議アクセス番号を作成します。  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |ダイヤルイン会議の構成設定の新しいコレクションを作成します。 これらの設定では、ユーザーがダイヤルイン会議に参加または退出するときに Skype for Business Server がどのように応答するかが決定されます。 特に、参加者が会議の参加時に名前を記録する必要があるかどうか、およびユーザーの通話参加時や通話終了時のシステムからの通知方法 (または、通知するかどうか) に関する情報を戻します。  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定の新しいコレクションを作成します。  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |新しいダイヤル プランを作成します。  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |既存の会議ディレクトリを削除します。 会議ディレクトリは、ダイヤルイン会議ユーザーが会議情報を検索するのに役立ちます。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議のアクセス番号を削除します。  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |1 つまたは複数のダイヤルイン会議の構成設定のコレクションを削除します。 これらの設定では、ユーザーがダイヤルイン会議に参加または退出するときに Skype for Business Server がどのように応答するかが決定されます。  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用されるデュアルトーン多周波数 (DTMF) シグナリング設定の既存のコレクションを削除します。  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号のプロパティ値を変更します。 ダイヤルイン会議により、ユーザーは、公衆交換電話網 (PSTN) で "固定" 電話、携帯電話、またはその他のデバイスを使用して、会議のオーディオ部分に参加できます。  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーがダイヤルイン会議に参加または退出するときに Skype for Business Server が応答する方法を決定する設定を変更します。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定を変更します。  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |既存のダイヤル プランを変更します。  <br/> |
   
**PIN ポリシー設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |組織での使用に構成されている、クライアントの暗証番号 (PIN) のポリシーに関する情報を戻します。 PIN 認証を使用すると、ユーザー名とパスワードの代わりに PIN を指定して、Skype for Business Server にアクセスできます。  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |クライアントの暗証番号 (PIN) ポリシーをユーザーまたはユーザーのグループに割り当てます。  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |新しいクライアント暗証番号 (PIN) ポリシーを作成します。  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |指定された暗証番号 (PIN) ポリシーを削除します。  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |1 つ以上の既存のクライアント個人識別番号 (PIN) ポリシーを変更します。  <br/> |
   
**その他の会議の設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Skype for Business Server ミーティング ルームを無効にします。 会議室は、狭い会議室でのビデオ会議やグループ作業のシナリオに対応できる会議デバイスです。 会議室オブジェクトを無効にすると、会議室を表すユーザー アカウントに割り当てられている Skype for Business Server 固有の Active Directory 属性すべてが削除されます。 ただし、Active Directory ユーザー アカウント自体は削除されません。  <br/> |
|[Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Skype for Business Server ミーティング ルームを有効にします。 ミーティング ルームを有効にするには、まずそのシステムを表す Active Directory のユーザー アカウントを作成する必要があります。 ミーティング ルーム オブジェクトはユーザー アカウントに基づきますが、これらのオブジェクトは Get-CsUser コマンドレットを実行したときには表示されません。  <br/> |
|[Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |組織で使用される会議の免責事項に関する情報を戻します。 会議の免責事項は、ハイパーリンクを使用して会議に参加するユーザー (たとえば、Windows Internet Explorer などのブラウザーに会議へのリンクを貼り付けているユーザー) に表示されるメッセージです。  <br/> |
|[Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |組織で使用するように構成された Skype for Business Server ミーティング ルームに関する情報を返します。  <br/> |
|[Move-CsMeetingRoom](/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Skype for Business Server ミーティング ルーム オブジェクトをレジストラー プール間で移動します。  <br/> |
|[Remove-CsConferenceDisclaimer](/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |組織で使用される会議免責事項のヘッダーと本文のテキストをクリアします。 会議についての免責事項は、ハイパーリンクを使用して会議に参加するユーザー (たとえば、Windows Internet Explorer などのブラウザーに会議へのリンクを貼り付けたユーザー) に表示されるメッセージです。  <br/> |
|[Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |既存の Skype for Business Server ミーティング ルームのプロパティ値を変更します。  <br/> |
   
**テスト設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Test-CsASConference](/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |1 組のユーザーがアプリケーション共有電話会議に参加できるかどうかをテストします。  <br/> |
|[Test-CsAudioConferencingProvider](/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |ユーザーが自分の電話会議プロバイダーに接続できるかをテストします。電話会議プロバイダーとは、電話会議サービスを組織に提供するサード パーティの企業です。電話会議プロバイダーの主な機能は、社外にいて企業ネットワークまたはインターネットに接続されていないユーザーが、電話会議または会議のオーディオ部分に参加できるようにすることです。  <br/> |
|[Test-CsAVConference](/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |2 人のユーザーが音声/ビデオ (A/V) 会議に参加する機能をテストします。  <br/> |
|[Test-CsDataConference](/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |PowerPoint スライド、ホワイトボード、ポーリングの共有や表示などのアクティビティを含む Skype for Business Server Web 会議に 2 人のユーザーが参加できるかどうかを確認します。 また、このコマンドレットは、Skype for Business Server Web 会議サービスが Office Web Apps Server を検出し、クライアントが Office Web Apps Server によってブロードキャストするための PowerPoint ファイルをアップロードできる点も確認します。  <br/> |
|[Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |ユーザーがダイヤルイン会議セッションに参加できるのか確認します。  <br/> |
|[Test-CsDialPlan](/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |電話番号をダイヤル プラン (以前は場所プロファイルと呼ばれる) に対してテストし、正規化ルールが適用された後に、その番号と翻訳された番号に適用される正規化ルールを返します。  <br/> |
|[Test-CsMcxConference](/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |3 人のユーザーが Skype for Business Server Mobility Service 会議に参加する機能をテストします。 Mobility Service を使用すると、iPhone や Windows Phone などの携帯電話のユーザーは、インスタント メッセージやプレゼンス情報の交換などの操作を実行できます。ワイヤレス プロバイダーではなく、内部的にボイス メールを保存および取得する。また、Skype for Business Server の機能 ([仕事経由通話] や [ダイヤルアウト会議] など) を利用できます。  <br/> **注:** MCX を使用するクライアントは、Skype for Business Server 2019 ではサポートされていません。|
|[Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |2 人のユーザーがユニファイド コミュニケーション Web API (UCWA) を使用してオンライン会議をスケジュール、参加、実行する機能をテストします。  <br/> |
|[Debug-CsDataConference](/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Skype for Business Server に含まれるデータ会議機能の診断情報を返します。  <br/> |
