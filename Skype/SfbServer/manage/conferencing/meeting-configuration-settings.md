---
title: 会議の構成設定を管理Skype for Business Server
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '概要: 会議の構成設定を管理する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 9bd0cefb32074f6e11d524e65096fa0999db4ae35b5244c202616d76ded81085
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321679"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>会議の構成設定を管理Skype for Business Server
 
**概要:** 会議の構成設定を管理する方法については、Skype for Business Server。
  
このトピックでは、会議の構成設定を管理する方法について説明します。 会議を計画および展開する方法の詳細については、「会議を[](../../plan-your-deployment/conferencing/conferencing.md)計画する」および「Skype for Business Serverでの会議の展開」を[参照](../../deploy/deploy-conferencing/deploy-conferencing.md)Skype for Business Server。
  
会議の構成設定は、匿名ユーザーとダイヤルイン会議ユーザーがこれらの会議に参加する方法 (または場合によっては) を制御するだけでなく、ユーザーが作成できる会議の種類を決定します。 これらの設定は、スケジュールされた会議にのみ影響を与える点に注意してください。ユーザーは、会議の [今すぐ会議] オプションをクリックして作成されたアドホック会議にはSkype for Business。
  
会議の構成設定では、次の設定を定義します。
  
- 公衆交換電話網 (PSTN) からダイヤルインするユーザーをロビーに移動するかどうか
    
- 発表者の条件
    
- 会議の種類を既定で割り当てるかどうか
    
- 匿名 (認証されていない) ユーザーを既定で許可するかどうか
    
会議の特性は、コントロール パネルを使用するかSkype for Business Server管理シェルを使用Skype for Business Server定義できます。 
  
会議の設定は、グローバル レベル (既定で作成)、サイト レベル、またはプール レベルで指定できます。 既定では、グローバル設定は会議のエクスペリエンスを定義します。 プール レベル設定を作成すると、その設定は、そのプールがホストするすべての会議に適用されます。 プール レベル設定を作成しない場合は、サイト レベル設定が存在すればそれが適用されます。 サイト レベル設定を定義しない場合は、グローバル設定がすべての会議に適用されます。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用して会議Skype for Business Server管理する

コントロール パネルを使用して会議Skype for Business Server管理するには、次の操作を行います。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して会議Skype for Business Server管理する

管理シェルを使用して会議Skype for Business Serverするには、次のコマンドレットを使用します。
  
**会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用されている会議構成設定に関する情報を返します。  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |サイトまたはサービス スコープで会議構成設定の新しいコレクションを作成します。  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |会議構成設定の既存のコレクションを削除します。  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用されている会議の構成設定を変更します。  <br/> |
