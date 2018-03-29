---
title: Skype for Business Server 2015 での電話会議サーバー構成設定の管理
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '概要: ビジネス サーバー 2015 の Skype で会議サーバーの構成設定を管理する方法を説明します。'
ms.openlocfilehash: 88c127acdd569945eddb41e997034e5ea23ea2a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での電話会議サーバー構成設定の管理
 
**の概要:**ビジネス サーバー 2015 の Skype で会議サーバーの構成設定を管理する方法について説明します。
  
このトピックでは、会議サーバーの構成設定を管理する方法について説明します。 予定し、会議を展開する方法の詳細については、[ビジネス サーバー 2015 の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)および[ビジネス サーバー 2015 の Skype での展開の会議](../../deploy/deploy-conferencing/deploy-conferencing.md)を参照してください。
  
会議構成設定の決定など、サイズが最大の会議の内容と配布資料です。アプリケーション共有会議サービス用の帯域幅の最大値格納域の制限と有効期限です。内部および外部の Url がサポートされているクライアントのダウンロードします。ユーザーが会議のヘルプとリソースを取得できる内部および外部の Url へのポインターアプリケーションの共有、クライアント側のオーディオ、ファイル転送、およびメディア トラフィックに使用するポートです。 これらの設定を使用すると、実際のサーバーそのものを管理できます。 Skype ビジネス サーバー管理シェルを使用してこれらの設定を設定できます。
  
ビジネス サーバーの Skype をインストールするときにシステムで会議の単一のコレクション (グローバル コレクション) の構成設定。 サイトまたはサービス用のカスタム設定を作成する場合は、**新規 CsConferencingConfiguration**コマンドレットを使用してこれを行うことができます。 サイトまたはサービス スコープでのみ新しい設定を適用できることに注意してください。構成の設定、会議の新しいグローバル コレクションを作成できませんが、**セット CsConferencingConfiguration**コマンドレットを使用してグローバル コレクションを変更することができます。 さらに、サイトまたはサービスをホストできますなしの設定の 1 つ以上のコレクションです。 しようとするとサイトと、レドモンドは、レドモンドの新しい設定を作成するサイトは既にホスト会議構成設定のコレクションから、コマンドは失敗します。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>ビジネス サーバー管理シェルの Skype を使用して、会議構成設定を管理します。

Skype ビジネス サーバー管理シェルを使用して会議の構成の設定を管理するには、次のコマンドレットを使用します。
  
**会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |電話会議の構成設定に関する情報を戻します。  <br/> |
|[新しい-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |電話会議の構成設定の新しいコレクションを作成します。  <br/> |
|[削除 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |指定した電話会議の構成設定のコレクションを削除します。  <br/> |
|[セット CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |電話会議の構成設定の既存のコレクションを変更します。  <br/> |
   
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
  

