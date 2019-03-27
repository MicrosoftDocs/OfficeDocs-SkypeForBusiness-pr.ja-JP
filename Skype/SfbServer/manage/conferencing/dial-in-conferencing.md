---
title: ビジネス サーバーの Skype では、ダイヤルイン会議を管理します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: '概要: ビジネス サーバーの Skype では、ダイヤルイン会議を管理する方法を説明します。'
ms.openlocfilehash: 109f40e66feda81098f09689a862ce219ac2f676
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884937"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>ビジネス サーバーの Skype では、ダイヤルイン会議を管理します。
 
**の概要:** ビジネス サーバーの Skype では、ダイヤルイン会議を管理する方法について説明します。
  
このトピックでは、ダイヤルイン会議を管理する方法について説明します。 計画および展開にダイヤルイン会議を構成する方法の詳細については、 [Skype のビジネス サーバーにダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)と[Skype のビジネス サーバーにダイヤルイン会議の構成](../../deploy/deploy-conferencing/dial-in-conferencing.md)を参照してください。
  
ダイヤルイン会議を管理するために次のタスクを実行することができます: を有効にするまたはダイヤルイン会議を無効にする、アクセス番号を管理、ダイヤルイン会議の暗証番号 (pin) ポリシーを管理、会議の参加を管理し、お知らせのままに、DTMF のキー マッピングを変更します。コマンド、および [ようこそ] ユーザーがダイヤルイン会議。 
  
ダイヤル プランを管理する方法の詳細についてを参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。
  
PSTN 使用法の詳細については、[音声ポリシーを構成する、PSTN 使用法レコード、およびビジネスのための Skype でのボイス ルート](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)を参照してください。
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、ダイヤルイン会議を管理します。

ダイヤルイン会議に関する情報を管理するには:
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックします。
    
ダイヤル プランと PSTN 使用法に関する情報を管理するには:
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用してダイヤルイン会議を管理します。

ビジネス サーバー管理シェルの Skype を使用して、ダイヤルイン会議を管理するためには、次のコマンドレットを使用します。
  
**ダイヤルイン会議の設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |組織用に構成された電話会議ディレクトリに関する情報を戻します。電話会議ディレクトリは、ダイヤルイン会議ユーザーが電話会議情報を検索するのに役立ちます。  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーが参加またはダイヤルイン会議のままにするときの Skype ビジネス サーバーの応答に関する情報を取得します。  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |組織で使用するように構成されているすべてのダイヤルイン会議アクセス番号に関する情報を戻します。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議で使用されるデュアルトーン多重周波数 (DTMF) の信号設定を戻します。DTMF を使用すると、会議にダイヤルインするユーザーは、電話のキーパッドで会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |ビジネス サーバーにダイヤルイン会議の Skype での使用はサポートされて、地域と少数株主の言語を含む言語の一覧を返します。 これらの言語は、電話を使用して電話会議に出席しているユーザーにオーディオ メッセージと指示を中継するときに使用されます。  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |組織で使用されるダイヤル プランに関する情報を戻します。  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |ダイヤル プランを、1 つまたは複数のユーザーあるいはグループに割り当てます。  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |ビジネス サーバーの会議ディレクトリを Microsoft Office 通信 Server 2007 R2 から Skype にインポートします。 これにより、Skype のビジネス サーバーと Office 通信 Server 2007 の R2 の間の相互運用性を提供します。  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |既存の電話会議ディレクトリをあるプールから別のプールに移動します。  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |組織で使用する新しい電話会議ディレクトリを作成します。  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |新しいダイヤルイン会議アクセス番号を作成します。  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |ダイヤルイン会議の構成設定の新しいコレクションを作成します。 これらの設定は、ユーザーが参加またはダイヤルイン会議のままにするときの Skype ビジネス サーバーの応答を決定します。 特に、参加者が電話会議の参加時に名前を記録する必要があるかどうか、およびユーザーの通話参加時や通話終了時のシステムからの通知方法 (または、通知するかどうか) に関する情報を戻します。  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定の新しいコレクションを作成します。  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |新しいダイヤル プランを作成します。  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |既存の電話会議ディレクトリを削除します。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号を削除します。  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |1 つまたは複数のダイヤルイン会議の構成設定のコレクションを削除します。 これらの設定は、ユーザーが参加またはダイヤルイン会議のままにするときの Skype ビジネス サーバーの応答を決定します。  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定の既存のコレクションを削除します。  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号のプロパティ値を変更します。  <br/> |
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
   

