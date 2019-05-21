---
title: Skype for Business Server で会議サーバーの構成設定を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '概要: Skype for Business Server で会議サーバーの構成設定を管理する方法について説明します。'
ms.openlocfilehash: 190cd78e3c81f98859c40fe386fae2c4fd934a8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289000"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で会議サーバーの構成設定を管理する
 
**概要:** Skype for Business Server で会議サーバーの構成設定を管理する方法について説明します。
  
このトピックでは、会議サーバーの構成設定を管理する方法について説明します。 会議の計画と展開の詳細については、「Skype for business [server で会議の計画を立てる](../../plan-your-deployment/conferencing/conferencing.md)」および「 [Skype for business server で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)する」を参照してください。
  
会議の構成の設定では、会議コンテンツと配布資料で許可される最大サイズなどの項目を指定します。アプリケーション共有会議サービスの最大帯域幅。記憶域の制限と有効期間サポートされているクライアントの内部および外部ダウンロードの Url。ユーザーが会議のヘルプとリソースを取得できる内部と外部の Url へのポインター。アプリケーション共有、クライアントオーディオ、ファイル転送、メディアトラフィックに使用されるポート。 これらの設定により、実際のサーバーそのものを管理できます。 これらの設定は、Skype for Business Server 管理シェルを使用して設定できます。
  
Skype for Business Server をインストールすると、会議構成設定 (グローバルコレクション) の1つのコレクションが提供されます。 サイトまたはサービスのカスタム設定を作成する必要がある場合は、 **CsConferencingConfiguration**コマンドレットを使用して行うことができます。 新しい設定は、サイトまたはサービスの範囲に対してのみ適用されることに注意してください。会議の構成設定の新しいグローバルコレクションを作成することはできませんが、 **CsConferencingConfiguration**コマンドレットを使用してグローバルコレクションを変更することができます。 さらに、サイトまたはサービスでは、複数の設定のコレクションをホストすることはできません。 Redmond サイトの新しい設定を作成しようとしたときに、Redmond サイトが既に会議構成設定のコレクションをホストしている場合、コマンドは失敗します。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議構成設定を管理する

Skype for Business Server 管理シェルを使用して会議構成設定を管理するには、次のコマンドレットを使用します。
  
**電話会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |電話会議の構成設定に関する情報を戻します。  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |電話会議の構成設定の新しいコレクションを作成します。  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |指定した電話会議の構成設定のコレクションを削除します。  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |電話会議の構成設定の既存のコレクションを変更します。  <br/> |
   
例 1 に示すコマンドは、Redmond サイト (site:Redmond) の会議構成設定の新しいコレクションを作成します。この例には、Organization プロパティの値を Litwareinc に設定するために使用される追加のパラメーター (Organization) が 1 つ含まれています。 
  
```
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

このようなコレクションは、1 サイトにつき 1 つしか存在できません。Redmond サイトに既に会議構成設定のコレクションがある場合、このコマンドは失敗します。 
  
次の例では、会議構成設定の新しいコレクションを定義します。これらの構成設定は、最初はメモリ内に格納され、後で Redmond サイトに適用されます。 
  
最初のコマンドで **New-CsConferencingConfiguration** コマンドレットを使用して、設定に関する新しいメモリ内コレクションを作成し、変数 $x に格納します。 InMemory パラメーターを使用して、コレクションを直ちに Redmond サイトに適用する代わりに、メモリ内に作成するように指定します。
  
コレクションの作成後、2 番目のコマンドで Organization プロパティの値に Litwareinc を設定しています。 
  
最後に 3 番目のコマンドで、**Set-CsConferencingConfiguration** コマンドレットを使用して新しい設定を Redmond サイトに実際に適用します。
  
```
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

**Set-CsConferencingConfiguration** コマンドレットを呼び出さない場合、変更は有効になりません。 Windows PowerShell セッションの終了後または変数 $x の削除後、すぐに消滅します。
  

