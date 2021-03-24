---
title: Skype for Business Server で会議ポリシーを管理する
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '概要: Skype for Business Server で会議ポリシーを管理する方法について説明します。'
ms.openlocfilehash: 39855aac09b88852d0931c9b8fbdb8e2e9187c71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099103"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server で会議ポリシーを管理する
 
**概要:** Skype for Business Server で会議ポリシーを管理する方法について説明します。
  
このトピックでは、会議ポリシーを管理する方法について説明します。 会議を計画および展開する方法の詳細については [、「Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) での会議の計画」および「Skype for Business Server での会議の展開 [」を参照してください](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
会議ポリシーを使用すると、会議に IP オーディオとビデオを含めるかどうかから、出席できる最大人数まで、さまざまなスケジュールと参加オプションを定義できます。 会議ポリシーを使用して、会議のセキュリティ、帯域幅、法的側面を管理できます。
  
会議ポリシーは、グローバル スコープ、サイト スコープ、およびユーザー スコープの 3 つのレベルで定義できます。 設定の対象になるのは、最も狭いスコープから最も広いスコープまでのどのスコープでも、特定のユーザーです。 ユーザーにポリシーを割り当てる場合、これらの設定が優先されます。 ユーザー ポリシーを割り当てていない場合は、サイト設定が適用されます。 ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル ポリシーが既定の設定を提供します。
  
グローバル ポリシーは既定として存在するため、新しいグローバル ポリシーを作成することはできません。 また、既存のグローバル ポリシーを削除することはできませんが、既存のグローバル ポリシーを変更して既定の設定をカスタマイズすることはできます。
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議ポリシーを管理する

Skype for Business Server コントロール パネルを使用して会議ポリシーを管理するには、次の操作を行います。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議ポリシーを管理する

Skype for Business Server 管理シェルを使用して会議を管理するには、次のコマンドレットを使用します。
  
**会議ポリシーの設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |組織で使用するように構成されている会議ポリシーに関する情報を返します。  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |ユーザーごとのスコープで会議ポリシーを割り当てます。  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |組織で使用する新しい会議ポリシーを作成します。  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |指定した会議ポリシーを削除します。  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |既存の会議ポリシーを変更します。  <br/> |
