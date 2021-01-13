---
title: Skype for Business Server で会議サーバーの構成設定を管理する
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '概要: Skype for Business Server で会議サーバーの構成設定を管理する方法について説明します。'
ms.openlocfilehash: 7f8714a4098285e955b559b2baf70d74957159a1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828287"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で会議サーバーの構成設定を管理する
 
**概要:** Skype for Business Server で会議サーバーの構成設定を管理する方法について説明します。
  
このトピックでは、会議の構成設定を管理する方法について説明します。 会議を計画および展開する方法の詳細については [、「Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) での会議の計画」および「Skype for Business Server での会議の展開」を [参照してください](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
会議の構成設定では、会議コンテンツと資料の最大許容サイズなどの決定を行います。アプリケーション共有会議サービスの最大帯域幅。ストレージの制限と有効期限サポートされているクライアントの内部および外部ダウンロードの URL。ユーザーが会議のヘルプとリソースを取得できる内部 URL および外部 URL へのポインター。アプリケーション共有、クライアント オーディオ、ファイル転送、およびメディア トラフィックに使用されるポート。 これらの設定を使用すると、実際のサーバー自体を管理できます。 これらの設定は、Skype for Business Server 管理シェルを使用して設定できます。
  
Skype for Business Server をインストールすると、会議構成設定の単一のコレクション (グローバル コレクション) がシステムによって提供されます。 サイトまたはサービスに対してカスタム設定を作成する必要がある場合は、**New-CsConferencingConfiguration** コマンドレットを使用してその作業を行うことができます。 新しい設定は、サイトスコープまたはサービス スコープでのみ適用できます。会議構成設定の新しいグローバル コレクションを作成することはできませんが **、Set-CsConferencingConfiguration** コマンドレットを使用してグローバル コレクションを変更できます。 また、いかなるサイトやサービスも、設定のコレクションは 1 つしかホストできません。 Redmond サイト向けの新しい設定を作成しようとしても、Redmond サイトが既に会議構成設定のコレクションをホストしている場合、そのコマンドは失敗します。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議の構成設定を管理する

Skype for Business Server 管理シェルを使用して会議構成設定を管理するには、次のコマンドレットを使用します。
  
**会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |組織の会議構成設定に関する情報を戻します。  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |会議構成設定の新しいコレクションを作成します。  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |指定された会議構成設定のコレクションを削除します。  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |会議構成設定の既存のコレクションを変更します。  <br/> |
   
次のコマンドは、Redmond サイト (site:Redmond) の会議構成設定の新しいコレクションを作成します。 この例では、Organization プロパティの値を Litwareinc に設定するために使用される追加のパラメーター (Organization) が 1 つ含まれています。 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

このようなコレクションはサイトごとに 1 つしか持てないので、Redmond サイトに会議構成設定のコレクションが既に存在する場合、このコマンドは失敗します。 
  
次の例では、最初にメモリに格納され、後で Redmond サイトに適用される会議構成設定の新しいコレクションを定義します。 
  
最初のコマンドでは **、New-CsConferencingConfiguration** コマンドレットを使用して、変数データベースに格納されている設定の新しいメモリ内コレクションを作成$x。 InMemory パラメーターは、Redmond サイトにすぐに適用するのではなく、メモリ内にコレクションを作成する必要を指定します。
  
コレクションの作成後、2 番目のコマンドで Organization プロパティの値に Litwareinc を設定しています。 
  
最後に、3 番目のコマンドで **Set-CsConferencingConfiguration** コマンドレットを使用して、新しい設定を実際に Redmond サイトに適用します。
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

**Set-CsConferencingConfiguration** コマンドレットを呼び出さない場合、新しい設定が有効になります。 代わりに、セッションを終了するか、変数を削除するとすぐにWindows PowerShellに表示$x。
  

