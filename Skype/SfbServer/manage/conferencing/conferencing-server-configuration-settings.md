---
title: 会議サーバーの構成設定を管理Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '概要: 会議サーバー構成設定を管理する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 1435c6bd69624d5097d0377ab920ac9fed577072
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393779"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>会議サーバーの構成設定を管理Skype for Business Server
 
**概要:** 会議サーバー構成設定を管理する方法については、Skype for Business Server。
  
このトピックでは、会議の構成設定を管理する方法について説明します。 会議を計画および展開する方法の詳細については、「会議を[](../../plan-your-deployment/conferencing/conferencing.md)計画する」および「Skype for Business Serverでの会議の展開」を[参照](../../deploy/deploy-conferencing/deploy-conferencing.md)Skype for Business Server。
  
会議の構成設定は、会議のコンテンツと資料の最大許容サイズなどの設定を決定します。アプリケーション共有会議サービスの最大帯域幅。ストレージの制限と有効期限。サポートされているクライアントの内部および外部ダウンロードの URL。ユーザーが会議のヘルプとリソースを取得できる内部および外部 URL へのポインター。アプリケーション共有、クライアント オーディオ、ファイル転送、およびメディア トラフィックに使用されるポート。 これらの設定を使用すると、実際のサーバー自体を管理できます。 これらの設定は、管理シェルを使用Skype for Business Server設定できます。
  
サーバーをインストールSkype for Business Server、会議構成設定 (グローバル コレクション) の 1 つのコレクションが提供されます。 サイトまたはサービスに対してカスタム設定を作成する必要がある場合は、**New-CsConferencingConfiguration** コマンドレットを使用してその作業を行うことができます。 新しい設定は、サイトまたはサービス スコープでのみ適用できます。会議構成設定の新しいグローバル コレクションを作成することはできませんが、 **Set-CsConferencingConfiguration** コマンドレットを使用してグローバル コレクションを変更できます。 また、いかなるサイトやサービスも、設定のコレクションは 1 つしかホストできません。 Redmond サイト向けの新しい設定を作成しようとしても、Redmond サイトが既に会議構成設定のコレクションをホストしている場合、そのコマンドは失敗します。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して会議の構成Skype for Business Server管理する

管理シェルを使用して会議構成設定をSkype for Business Serverするには、次のコマンドレットを使用します。
  
**会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |組織の会議構成設定に関する情報を返します。  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |会議構成設定の新しいコレクションを作成します。  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |指定した会議構成設定のコレクションを削除します。  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |会議構成設定の既存のコレクションを変更します。  <br/> |
   
次のコマンドは、Redmond サイト (site:Redmond) の会議構成設定の新しいコレクションを作成します。 この例では、Organization プロパティの値を Litwareinc に設定するために使用される追加のパラメーター (Organization) が 1 つ含まれています。 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

このようなコレクションはサイトごとに 1 つしか持てないので、Redmond サイトに既に会議構成設定のコレクションがある場合、このコマンドは失敗します。 
  
次の例では、最初はメモリに格納され、後で Redmond サイトに適用される会議構成設定の新しいコレクションを定義します。 
  
最初のコマンドでは **、New-CsConferencingConfiguration** コマンドレットを使用して、変数 $x に格納されている設定の新しいメモリ内コレクションを作成します。 InMemory パラメーターは、Redmond サイトにすぐに適用するのではなく、コレクションをメモリ内に作成する必要があります。
  
コレクションの作成後、2 番目のコマンドで Organization プロパティの値に Litwareinc を設定しています。 
  
最後に、3 番目のコマンドは **Set-CsConferencingConfiguration** コマンドレットを使用して、新しい設定を実際に Redmond サイトに適用します。
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

**Set-CsConferencingConfiguration** コマンドレットを呼び出さない場合、新しい設定は有効ではありません。 代わりに、セッションを終了するか、または変数を削除すると、Windows PowerShell表示されなくなります$x。
