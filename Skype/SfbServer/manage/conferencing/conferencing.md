---
title: ビジネスのサーバーに対して Skype で会議を管理します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: '概要: ビジネス サーバーの Skype で会議を管理する方法を説明します。'
ms.openlocfilehash: 683da834b6de82d9da857ad4ab0a07e2ac4a6731
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895126"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>ビジネスのサーバーに対して Skype で会議を管理します。
 
**の概要:** ビジネス サーバーの Skype で会議を管理する方法について説明します。
  
このトピックでは、電話会議を管理する方法について説明します。 予定し、会議を展開する方法の詳細については、[ビジネスのサーバー用の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)と[ビジネス サーバーの Skype で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)を参照してください。
  
ビジネス サーバーの Skype では、次のように構成し、ポリシー設定を指定することによって会議の詳細を管理します。 いる用語の会議と会議も同義的に用いに注意してください。 ですが、一般に、会議会議の特定のインスタンスとして考えることができます。
  
- **電話会議ポリシー設定**には、会議に IP オーディオと IP ビデオを組み込むことができるかどうかということから、出席可能な最大参加者数に至るまでの、さまざまなスケジューリングおよび参加オプションが含まれます。 管理者は、電話会議ポリシーを使用して、セキュリティ、帯域幅、および会議の法的側面を管理できます。
    
    電話会議ポリシーはユーザーまたはサイトに適用され、特定の会議には適用できません。 したがって、会議の会議出席依頼には、事前にいくつかの週を作成できますが、会議が開始される直前にビジネス アカウントは、会議の開催者の Skype に、限定的な会議のポリシーを適用します。 
    
    会議の開催者の役割に専用のアカウントが使用される場合は、電話会議ポリシーをそのアカウントに割り当てたままにすることができます。 会議の開催者は、ビジネス アカウントの全般的な Skype を使用する場合は、会議が終了した後、ポリシーを削除してください。
    
- **会議の構成設定**では、ユーザーが作成できる会議の種類を指定でき、さらにこの会議への匿名ユーザーやダイヤルイン会議ユーザーの参加方法について (または、参加可能かどうかについても) 制御できます。これらの設定は予定された会議にのみ影響します。会議の構成は、プールごと、サイトごと、またはグローバルに適用されます。
    
- **会議構成設定**の決定など、サイズが最大の会議の内容と配布資料です。アプリケーション共有会議サービス用の帯域幅の最大値格納域の制限と有効期限です。内部および外部の Url がサポートされているクライアントのダウンロードします。ユーザーが会議のヘルプとリソースを取得できる内部および外部の Url へのポインターアプリケーションの共有、クライアント側のオーディオ、ファイル転送、およびメディア トラフィックに使用するポートです。
    
    これらの設定により、実際のサーバーそのものを管理できます。 これらの設定は、Skype ビジネス サーバー管理シェルを使用してのみ設定できます。 
    
- **ダイヤルイン アクセスの設定**では、ユーザーが電話からダイヤルインできるかどうかと、可能な場合はその方法に関する情報を定義できます。 アクセス番号など、ダイヤルイン アクセス情報の一部はコントロール パネルの [会議] タブから指定し、ダイヤル プラン、音声ポリシー、ルート、PSTN 使用法などのダイヤルイン情報の一部はコントロール パネルの [音声ルーティング] タブから指定します。
    
- **PIN ポリシーの設定**では、参加者がダイヤルイン アクセスに使用する PIN を命名および定義できます。
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、またはビジネス サーバー管理シェルの Skype を使用して、会議を管理します。

ビジネス サーバーのコントロール パネルの Skype を使用して、またはビジネス サーバー管理シェルの Skype を使用して、ほとんどの会議のポリシーおよび構成設定を管理できます。 構成設定の一部は、Skype を使用してビジネス サーバー管理シェルでのみ利用できます。
  
- 電話会議ポリシーの設定を管理するには:
    
  - コントロール パネルで、**[会議]、[会議ポリシー] **の順に選択します。
    
  - PowerShell で、**-CsConferencingPolicy** の一連のコマンドレットを検索します。
    
- 会議の構成設定を管理するには:
    
  - コントロール パネルで、**[会議]、[会議の構成]** の順に選択します。
    
  - ビジネス サーバー管理シェルの Skype は、 **- CsMeetingConfiguration**コマンドレットを検索します。
    
- ダイヤルイン アクセス番号の設定を管理するには:
    
  - コントロール パネルで、**[会議]、[ダイヤルイン アクセス番号]** の順に選択します。
    
  - ビジネス サーバー管理シェルの Skype、 **- CsDialInConferencing**コマンドレットを検索します。
    
- ダイヤル プラン、音声ポリシー、ルート、および PSTN 使用法などのダイヤルイン アクセス情報を管理するには: 
    
  - コントロール パネルで、**[会議]、[音声ルーティング]** の順に選択します。
    
  - ビジネス サーバー管理シェルの Skype は、 **- CsDialPlan**と **- CsVoice**コマンドレットを検索します。
    
- PIN のポリシー設定を管理するには:
    
  - コントロール パネルで、**[会議]、[PIN ポリシー]** の順に選択します。
    
  - ビジネス サーバー管理シェルの Skype は、 **- CsPinPolicy**コマンドレットを検索します。
    
- 会議構成設定を管理するには、ビジネス サーバー管理シェルを Skype を使用する必要があります。 **-CsConferencingConfiguration** の一連のコマンドレットを検索します。
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype ビジネス サーバー管理シェル コマンドレット

会議を管理するために次の Skype ビジネス サーバー管理シェル コマンドレットを使用できます。 
  
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
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |サイト スコープまたはサービス スコープで会議の構成設定の新しいコレクションを作成します。 これらの設定のみに影響を与えるスケジュールされたミーティングです。ビジネス用の Skype で即時会議のオプション] をクリックして作成、臨時会議には影響しません。  <br/> |
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
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーが参加またはダイヤルイン会議のままにするときの Skype ビジネス サーバーの応答に関する情報を取得します。  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |組織で使用するように構成されているすべてのダイヤルイン会議アクセス番号に関する情報を戻します。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議で使用されるデュアルトーン多重周波数 (DTMF) の信号設定を戻します。DTMF を使用すると、電話会議にダイヤルインするユーザーは、電話のキーパッドで電話会議の設定 (自身をミュートおよびミュート解除したり、電話会議をロックおよびロック解除したりするなど) を制御できます。  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |ビジネス サーバーにダイヤルイン会議の Skype での使用はサポートされて、地域と少数株主の言語を含む言語の一覧を返します。 これらの言語は、電話を使用して電話会議に出席しているユーザーにオーディオ メッセージと指示を中継するときに使用されます。  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |組織で使用されるダイヤル プランに関する情報を戻します。  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |ダイヤル プランを、1 つまたは複数のユーザーあるいはグループに割り当てます。  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |ビジネス サーバーの会議ディレクトリを Microsoft Office 通信 Server 2007 R2 から Skype にインポートします。 これにより、Skype のビジネス サーバーと Office 通信 Server 2007 の R2 の間の相互運用性を提供します。  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |既存の電話会議ディレクトリを別のプールに移動します。電話会議ディレクトリは、ダイヤルイン会議ユーザーが会議情報を検索するのに役立ちます。  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |組織で使用できるように新しい電話会議ディレクトリを作成します。電話会議ディレクトリは、ダイヤルイン会議ユーザーが電話会議情報を検索するのに役立ちます。  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |新しいダイヤルイン会議アクセス番号を作成します。  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |ダイヤルイン会議の構成設定の新しいコレクションを作成します。 これらの設定は、ユーザーが参加またはダイヤルイン会議のままにするときの Skype ビジネス サーバーの応答を決定します。 特に、参加者が電話会議の参加時に名前を記録する必要があるかどうか、およびユーザーの通話参加時や通話終了時のシステムからの通知方法 (または、通知するかどうか) に関する情報を戻します。  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定の新しいコレクションを作成します。  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |新しいダイヤル プランを作成します。  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |既存の電話会議ディレクトリを削除します。電話会議ディレクトリは、ダイヤルイン会議ユーザーが電話会議情報を検索するのに役立ちます。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号を削除します。  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |1 つまたは複数のダイヤルイン会議の構成設定のコレクションを削除します。 これらの設定は、ユーザーが参加またはダイヤルイン会議のままにするときの Skype ビジネス サーバーの応答を決定します。  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定の既存のコレクションを削除します。  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号のプロパティ値を変更します。ダイヤルイン会議により、ユーザーは、公衆交換電話網 (PSTN) で "固定" 電話、携帯電話、またはその他のデバイスを使用して、電話会議のオーディオ部分に参加できます。  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Skype ビジネス サーバーのでのユーザーが参加またはダイヤルイン会議のままにするときの応答方法を決定する設定を変更します。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定を変更します。  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |既存のダイヤル プランを変更します。  <br/> |
   
**PIN ポリシーの設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |組織での使用に構成されている、クライアント暗証番号 (PIN) ポリシーに関する情報を戻します。 暗証番号 (pin) 認証では、ビジネスのサーバーのユーザー名とパスワードの代わりに暗証番号 (pin) を提供することによって Skype にアクセスすることができます。  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |クライアント暗証番号 (PIN) ポリシーをユーザーまたはユーザー グループに割り当てます。  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |新しいクライアント暗証番号 (PIN) ポリシーを作成します。  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |指定した暗証番号 (PIN) ポリシーを削除します。  <br/> |
|[セット CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |1 つまたは複数の既存のクライアント暗証番号 (PIN) ポリシーを変更します。  <br/> |
   
**その他の電話会議の設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |ビジネス サーバーの会議室に、Skype を無効にします。 ミーティング ルームは、小さな会議室でのビデオ会議およびグループ作業のシナリオに対処する目的で設計された会議デバイスです。 会議室を無効にするとオブジェクトのすべての Skype の会議室を表すユーザー アカウントに割り当てられているビジネス サーバー固有の Active Directory 属性を削除します。 ただし、Active Directory ユーザー アカウント自体は削除されません。  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |ビジネス サーバーの会議室に、Skype を使用できます。 会議室を有効にするには、まずそのシステムを表す Active Directory のユーザー アカウントを作成する必要があります。 会議室オブジェクトはユーザー アカウントに基づきますが、これらのオブジェクトは Get-CsUser コマンドレットを実行したときには表示されません。  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |組織で使用される電話会議の免責事項に関する情報を戻します。電話会議の免責事項は、ハイパーリンクを使用して電話会議に参加するユーザー (たとえば、Windows Internet Explorer などのブラウザーに電話会議へのリンクを貼り付けているユーザー) に表示されるメッセージです。  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |会議室の組織で使用するために構成されているビジネスのサーバーのすべての Skype に関する情報を返します。  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |ビジネス サーバーの会議の 1 つのレジストラー プールから別のルーム オブジェクトの Skype を移動します。  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |組織で使用される電話会議免責事項のヘッダーと本文のテキストをクリアします。電話会議についての免責事項は、ハイパーリンクを使用して電話会議に参加するユーザー (たとえば、Windows Internet Explorer などのブラウザーに電話会議へのリンクを貼り付けたユーザー) に表示されるメッセージです。  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |会議室の業務サーバーの既存の Skype のプロパティ値を変更します。  <br/> |
   
**設定のテスト**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |1 組のユーザーがアプリケーション共有電話会議に参加できるかどうかをテストします。  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |ユーザーが自分の電話会議プロバイダーに接続できるかをテストします。電話会議プロバイダーとは、電話会議サービスを組織に提供するサード パーティの企業です。電話会議プロバイダーの主な機能は、社外にいて企業ネットワークまたはインターネットに接続されていないユーザーが、電話会議または会議のオーディオ部分に参加できるようにすることです。  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |1 組のユーザーが音声ビデオ (A/V) 会議に参加できるかどうかをテストします。  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |共有、PowerPoint のスライド、ホワイト ボードや投票を表示するなどの活動を含むビジネス サーバーの web 会議、Skype で 1 組のユーザーが参加できるかどうかを確認します。 コマンドレットでは、Business Server web 会議サービスの Skype が Office Web アプリケーション サーバーを検出できるし、クライアントが Office Web アプリケーション サーバーがブロードキャスト用の PowerPoint ファイルをアップロードできることも確認します。  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |ユーザーがダイヤルイン会議のセッションに参加できるかどうかを確認します。  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |電話番号のテストをダイヤル プラン (以前はロケーション プロファイルと呼ばれていました) に対して行い、その番号に適用される正規化ルールと、その正規化ルールが適用された後の変換された番号を戻します。  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Skype サーバー移動サービスのビジネス会議に参加する 3 人のユーザーの機能をテストします。 IPhones と exchange インスタント メッセージとプレゼンス情報としてこのような処理を実行する Windows の電話などの携帯電話のモバイル サービスができます。保存し、内部での代わりに、ワイヤレスのプロバイダーでのボイス メールを取得します。ビジネス サーバーなどの機能の作業とダイヤルアウト会議を使用して呼び出し Skype の活用してください。  <br/> **注:** ビジネス サーバー 2019 の Skype で、MCX を使用するクライアントがサポートされていません。|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |1 組のユーザーが Unified Communications Web API (UCWA) を使用してオンライン会議に対するスケジュール設定、参加、実施ができるかどうかをテストします。  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |ビジネス サーバーの Skype に含まれているデータ会議機能の診断情報を取得します。  <br/> |
   

