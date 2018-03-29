---
title: Skype for Business Server 2015 での会議の構成設定の管理
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '概要: を管理する方法を説明する会議出席ビジネス サーバー 2015 の Skype の設定を構成します。'
ms.openlocfilehash: 30b19eee5e298bfaa5eefe1eee50c9ea615b5682
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での会議の構成設定の管理
 
**の概要:**管理する方法については会議出席ビジネス サーバー 2015 の Skype の設定を構成します。
  
このトピックでは、会議の構成設定を管理する方法について説明します。 予定し、会議を展開する方法の詳細については、[ビジネス サーバー 2015 の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)および[ビジネス サーバー 2015 の Skype での展開の会議](../../deploy/deploy-conferencing/deploy-conferencing.md)を参照してください。
  
会議の構成設定を制御するだけでなく、ユーザーが作成できる会議の種類を決定する方法なども匿名ユーザーやダイヤルイン会議のユーザーがこれらの会議に参加できます。 これらの設定のみに影響を与えるスケジュールされたミーティングです。ビジネス用の Skype で即時会議のオプション] をクリックして作成、臨時会議には影響しません。
  
会議の構成設定では、次の設定を定義します。
  
- 公衆交換電話網 (PSTN) からダイヤルインするユーザーをロビーに移動するかどうか
    
- 発表者の条件
    
- 会議の種類を既定で割り当てるかどうか
    
- 匿名 (認証されていない) ユーザーを既定で許可するかどうか
    
ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、会議の特性を定義できます。 
  
指定できます (デフォルトで作成)、グローバル レベルの設定を達成するには、サイト レベルでは、または、プールのレベル。 既定では、グローバル設定が会議に関する操作性を定義します。 プール レベル設定を作成すると、その設定は、そのプールがホストするすべての会議に適用されます。 プール レベル設定を作成しない場合は、サイト レベル設定が存在すればそれが適用されます。 サイト レベル設定を定義しない場合は、グローバル設定がすべての会議に適用されます。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、会議の設定を管理します。

ビジネス サーバーのコントロール パネルの Skype を使用して、会議の設定の管理。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>ビジネス サーバー管理シェルの Skype を使用して、会議の設定を管理します。

Skype ビジネス サーバー管理シェルを使用して会議を管理するためには、次のコマンドレットを使用します。
  
**会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用されている会議の構成設定に関する情報を戻します。  <br/> |
|[新しい-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |サイト スコープまたはサービス スコープで会議の構成設定の新しいコレクションを作成します。  <br/> |
|[削除 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |会議の構成設定の既存のコレクションを削除します。  <br/> |
|[セット CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用されている会議の構成設定を変更します。  <br/> |
   

