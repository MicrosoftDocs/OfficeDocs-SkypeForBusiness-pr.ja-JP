---
title: Skype for Business Server で会議を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: '概要: Skype for Business Server で会議を管理する方法について説明します。'
ms.openlocfilehash: 321241be405789e5a8b0f9440fddd09f738911ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818628"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Skype for Business Server で会議を管理する
 
**概要:** Skype for Business Server で会議を管理する方法について説明します。
  
このトピックでは、電話会議を管理する方法について説明します。 会議の計画と展開の詳細については、「Skype for business [server で会議の計画を立てる](../../plan-your-deployment/conferencing/conferencing.md)」および「 [Skype for business server で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)する」を参照してください。
  
Skype for Business Server では、次のように構成とポリシーの設定を指定して、会議の詳細を管理します。 ただし、会議と会議という用語は、同じように使用されることがあります。 ただし、一般的には、会議を特定の会議のインスタンスとして考えることができます。
  
- **電話会議ポリシー設定**には、会議に IP オーディオと IP ビデオを組み込むことができるかどうかということから、出席可能な最大参加者数に至るまでの、さまざまなスケジューリングおよび参加オプションが含まれます。 管理者は、電話会議ポリシーを使用して、セキュリティ、帯域幅、および会議の法的側面を管理できます。
    
    電話会議ポリシーはユーザーまたはサイトに適用され、特定の会議には適用できません。 そのため、会議の出席依頼は何週間も前もって作成できますが、制限付き会議ポリシーは、会議の開始前に会議の開催者の Skype for Business アカウントに適用する必要があります。 
    
    会議の開催者の役割に専用のアカウントが使用される場合は、電話会議ポリシーをそのアカウントに割り当てたままにすることができます。 会議の開催者が一般的な Skype for Business アカウントを使用している場合は、会議が完了した後でポリシーを削除する必要があります。
    
- **会議の構成設定**では、ユーザーが作成できる会議の種類を指定でき、さらにこの会議への匿名ユーザーやダイヤルイン会議ユーザーの参加方法について (または、参加可能かどうかについても) 制御できます。これらの設定は予定された会議にのみ影響します。会議の構成は、プールごと、サイトごと、またはグローバルに適用されます。
    
- 会議の**構成の設定**では、会議コンテンツと配布資料で許可される最大サイズなどの項目を指定します。アプリケーション共有会議サービスの最大帯域幅。記憶域の制限と有効期間サポートされているクライアントの内部および外部ダウンロードの Url。ユーザーが会議のヘルプとリソースを取得できる内部と外部の Url へのポインター。アプリケーション共有、クライアントオーディオ、ファイル転送、メディアトラフィックに使用されるポート。
    
    これらの設定により、実際のサーバーそのものを管理できます。 これらの設定を設定するには、Skype for Business Server 管理シェルを使用する必要があります。 
    
- **ダイヤルイン アクセスの設定**では、ユーザーが電話からダイヤルインできるかどうかと、可能な場合はその方法に関する情報を定義できます。 アクセス番号など、ダイヤルイン アクセス情報の一部はコントロール パネルの [会議] タブから指定し、ダイヤル プラン、音声ポリシー、ルート、PSTN 使用法などのダイヤルイン情報の一部はコントロール パネルの [音声ルーティング] タブから指定します。
    
- **PIN ポリシーの設定**では、参加者がダイヤルイン アクセスに使用する PIN を命名および定義できます。
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して会議を管理する

Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して、ほとんどの会議ポリシーと構成設定を管理できます。 一部の構成設定は、Skype for Business Server 管理シェルを使用する場合にのみ利用できます。
  
- 電話会議ポリシーの設定を管理するには:
    
  - コントロール パネルで、**[会議]、[会議ポリシー] **の順に選択します。
    
  - PowerShell で、**-CsConferencingPolicy** の一連のコマンドレットを検索します。
    
- 会議の構成設定を管理するには:
    
  - コントロール パネルで、**[会議]、[会議の構成]** の順に選択します。
    
  - Skype for Business Server 管理シェルで、 **-cs会議構成**コマンドレットを検索します。
    
- ダイヤルイン アクセス番号の設定を管理するには:
    
  - コントロール パネルで、**[会議]、[ダイヤルイン アクセス番号]** の順に選択します。
    
  - Skype for Business Server 管理シェルで、 **-csの [会議**] コマンドレットを検索します。
    
- ダイヤル プラン、音声ポリシー、ルート、および PSTN 使用法などのダイヤルイン アクセス情報を管理するには: 
    
  - コントロール パネルで、**[会議]、[音声ルーティング]** の順に選択します。
    
  - Skype for Business Server 管理シェルで、 **-CsDialPlan**と**csvoice**のコマンドレットを検索します。
    
- PIN のポリシー設定を管理するには:
    
  - コントロール パネルで、**[会議]、[PIN ポリシー]** の順に選択します。
    
  - Skype for Business Server 管理シェルで、 **-CsPinPolicy**コマンドレットを検索します。
    
- 会議の構成設定を管理するには、Skype for Business Server 管理シェルを使用する必要があります。 **-CsConferencingConfiguration** の一連のコマンドレットを検索します。
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype for Business Server 管理シェルコマンドレット

会議を管理するために、次の Skype for Business Server 管理シェルコマンドレットを使用できます。 
  
**電話会議ポリシーの設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |組織で使用するように構成されている電話会議ポリシーに関する情報を戻します。電話会議ポリシーにより、電話会議で使用できる機能が決まります。これには、電話会議に IP オーディオと IP ビデオを組み込むことができるかということから、会議に出席可能な最大参加者数に至るまで、すべての機能が含まれます。  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |電話会議ポリシーをユーザーごとのスコープで割り当てます。  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |組織で使用するために新しい電話会議ポリシーを作成します。  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |指定の電話会議ポリシーを削除します。  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |既存の電話会議ポリシーを変更します。  <br/> |
   
**会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用中の会議の構成設定に関する情報を戻します。会議の構成設定では、ユーザーが作成できる会議の種類を指定でき、さらにこの会議への匿名ユーザーやダイヤルイン会議ユーザーの参加方法について (または、参加可能かどうかについても) 制御できます。  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |サイト スコープまたはサービス スコープで会議の構成設定の新しいコレクションを作成します。 これらの設定は、スケジュールされた会議にのみ影響します。Skype for Business の [今すぐ会議] オプションをクリックして作成されたアドホック会議には影響ありません。  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |会議の構成設定の既存のコレクションを削除します。  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用されている会議の構成設定を変更します。  <br/> |
   
**電話会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |組織用の電話会議の構成設定に関する情報を戻します。電話会議の設定は、電話会議コンテンツや配布資料の最大許容サイズ、コンテンツの猶予期間 (コンテンツが削除されるまでに保存される期間)、サポートされているクライアントの内部および外部ダウンロード用 URL などを決定します。  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |電話会議の構成設定の新しいコレクションを作成します。  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |指定した電話会議の構成設定のコレクションを削除します。  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |電話会議の構成設定の既存のコレクションを変更します。  <br/> |
   
**ダイヤルイン会議の設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |組織用に構成された電話会議ディレクトリに関する情報を戻します。電話会議ディレクトリは、ダイヤルイン会議ユーザーが電話会議情報を検索するのに役立ちます。  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーがダイヤルイン会議に参加または脱退したときに Skype for Business Server がどのように応答するかに関する情報を取得します。  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |組織で使用するように構成されているすべてのダイヤルイン会議アクセス番号に関する情報を戻します。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議で使用されるデュアルトーン多重周波数 (DTMF) の信号設定を戻します。DTMF を使用すると、電話会議にダイヤルインするユーザーは、電話のキーパッドで電話会議の設定 (自身をミュートおよびミュート解除したり、電話会議をロックおよびロック解除したりするなど) を制御できます。  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Skype for Business Server のダイヤルイン会議での使用がサポートされている地域/少数言語を含む言語のリストを返します。 これらの言語は、電話を使用して電話会議に出席しているユーザーにオーディオ メッセージと指示を中継するときに使用されます。  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |組織で使用されるダイヤル プランに関する情報を戻します。  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |ダイヤル プランを、1 つまたは複数のユーザーあるいはグループに割り当てます。  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Microsoft Office Communications Server 2007 R2 から Skype for Business Server に会議ディレクトリをインポートします。 これにより、Skype for Business Server と Office Communications Server 2007 R2 の間の相互運用性が提供されます。  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |既存の電話会議ディレクトリを別のプールに移動します。電話会議ディレクトリは、ダイヤルイン会議ユーザーが会議情報を検索するのに役立ちます。  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |組織で使用できるように新しい電話会議ディレクトリを作成します。電話会議ディレクトリは、ダイヤルイン会議ユーザーが電話会議情報を検索するのに役立ちます。  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |新しいダイヤルイン会議アクセス番号を作成します。  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |ダイヤルイン会議の構成設定の新しいコレクションを作成します。 この設定では、ユーザーがダイヤルイン会議に参加または脱退したときに Skype for Business Server がどのように応答するかを決定します。 特に、参加者が電話会議の参加時に名前を記録する必要があるかどうか、およびユーザーの通話参加時や通話終了時のシステムからの通知方法 (または、通知するかどうか) に関する情報を戻します。  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定の新しいコレクションを作成します。  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |新しいダイヤル プランを作成します。  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |既存の電話会議ディレクトリを削除します。電話会議ディレクトリは、ダイヤルイン会議ユーザーが電話会議情報を検索するのに役立ちます。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号を削除します。  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |1 つまたは複数のダイヤルイン会議の構成設定のコレクションを削除します。 この設定では、ユーザーがダイヤルイン会議に参加または脱退したときに Skype for Business Server がどのように応答するかを決定します。  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定の既存のコレクションを削除します。  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号のプロパティ値を変更します。ダイヤルイン会議により、ユーザーは、公衆交換電話網 (PSTN) で "固定" 電話、携帯電話、またはその他のデバイスを使用して、電話会議のオーディオ部分に参加できます。  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーがダイヤルイン会議に参加または脱退したときに Skype for Business Server がどのように応答するかを決定する設定を変更します。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定を変更します。  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |既存のダイヤル プランを変更します。  <br/> |
   
**PIN ポリシーの設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |組織での使用に構成されている、クライアント暗証番号 (PIN) ポリシーに関する情報を戻します。 PIN 認証を使用すると、ユーザーは、ユーザー名とパスワードの代わりに PIN を指定して、Skype for Business Server にアクセスできます。  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |クライアント暗証番号 (PIN) ポリシーをユーザーまたはユーザー グループに割り当てます。  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |新しいクライアント暗証番号 (PIN) ポリシーを作成します。  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |指定した暗証番号 (PIN) ポリシーを削除します。  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |1 つまたは複数の既存のクライアント暗証番号 (PIN) ポリシーを変更します。  <br/> |
   
**その他の電話会議の設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Skype for Business Server 会議室を無効にします。 ミーティング ルームは、小さな会議室でのビデオ会議およびグループ作業のシナリオに対処する目的で設計された会議デバイスです。 会議室オブジェクトを無効にすると、会議室を表すユーザーアカウントに割り当てられているすべての Skype for Business Server 固有の Active Directory 属性が削除されます。 ただし、Active Directory ユーザー アカウント自体は削除されません。  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Skype for Business Server 会議室を有効にします。 会議室を有効にするには、まずそのシステムを表す Active Directory のユーザー アカウントを作成する必要があります。 会議室オブジェクトはユーザー アカウントに基づきますが、これらのオブジェクトは Get-CsUser コマンドレットを実行したときには表示されません。  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |組織で使用される電話会議の免責事項に関する情報を戻します。電話会議の免責事項は、ハイパーリンクを使用して電話会議に参加するユーザー (たとえば、Windows Internet Explorer などのブラウザーに電話会議へのリンクを貼り付けているユーザー) に表示されるメッセージです。  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |組織で使用できるように構成されているすべての Skype for Business Server 会議室に関する情報を返します。  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Skype for Business Server 会議室オブジェクトをレジストラープール間で移動します。  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |組織で使用される電話会議免責事項のヘッダーと本文のテキストをクリアします。電話会議についての免責事項は、ハイパーリンクを使用して電話会議に参加するユーザー (たとえば、Windows Internet Explorer などのブラウザーに電話会議へのリンクを貼り付けたユーザー) に表示されるメッセージです。  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |既存の Skype for Business Server 会議室のプロパティ値を変更します。  <br/> |
   
**テストの設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |1 組のユーザーがアプリケーション共有電話会議に参加できるかどうかをテストします。  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |ユーザーが自分の電話会議プロバイダーに接続できるかをテストします。電話会議プロバイダーとは、電話会議サービスを組織に提供するサード パーティの企業です。電話会議プロバイダーの主な機能は、社外にいて企業ネットワークまたはインターネットに接続されていないユーザーが、電話会議または会議のオーディオ部分に参加できるようにすることです。  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |1 組のユーザーが音声ビデオ (A/V) 会議に参加できるかどうかをテストします。  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |PowerPoint スライド、ホワイトボード、投票の共有や表示などのアクティビティが含まれているユーザーのペアが Skype for Business Server web 会議に参加できるかどうかを確認します。 このコマンドレットは、Skype for Business Server web 会議サービスが Office Web Apps サーバーを検出し、クライアントが Office Web Apps サーバーによってブロードキャスト用の PowerPoint ファイルをアップロードできることも確認します。  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |ユーザーがダイヤルイン会議のセッションに参加できるかどうかを確認します。  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |電話番号のテストをダイヤル プラン (以前はロケーション プロファイルと呼ばれていました) に対して行い、その番号に適用される正規化ルールと、その正規化ルールが適用された後の変換された番号を戻します。  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |3人のユーザーが Skype for Business Server Mobility Service 会議に参加できるかどうかをテストします。 モバイルサービスを使うと、iPhones や Windows Phone などの携帯電話のユーザーは、exchange のインスタントメッセージやプレゼンス情報などの操作を行うことができます。ワイヤレスプロバイダーではなく、内部でボイスメールを保存して取得します。さらに、職場やダイヤルアウト会議などの Skype for Business Server 機能を活用できます。  <br/> **注:** MCX を使用するクライアントは、Skype for Business Server 2019 ではサポートされていません。|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |1 組のユーザーが Unified Communications Web API (UCWA) を使用してオンライン会議に対するスケジュール設定、参加、実施ができるかどうかをテストします。  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Skype for Business Server に含まれているデータ会議機能の診断情報を返します。  <br/> |
   

