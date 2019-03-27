---
title: 会議サーバーの構成設定で Skype のビジネス サーバーを管理します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '概要: ビジネス サーバーの Skype で会議サーバーの構成設定を管理する方法を説明します。'
ms.openlocfilehash: a12226f9f7d56f9f8a61b6f820a2c0f9744121fc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890382"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>会議サーバーの構成設定で Skype のビジネス サーバーを管理します。
 
**の概要:** 会議サーバーの構成設定で Skype のビジネス サーバーを管理する方法について説明します。
  
このトピックでは、会議サーバーの構成設定を管理する方法について説明します。 予定し、会議を展開する方法の詳細については、[ビジネスのサーバー用の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)と[ビジネス サーバーの Skype で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)を参照してください。
  
会議構成設定の決定など、サイズが最大の会議の内容と配布資料です。アプリケーション共有会議サービス用の帯域幅の最大値格納域の制限と有効期限です。内部および外部の Url がサポートされているクライアントのダウンロードします。ユーザーが会議のヘルプとリソースを取得できる内部および外部の Url へのポインターアプリケーションの共有、クライアント側のオーディオ、ファイル転送、およびメディア トラフィックに使用するポートです。 これらの設定により、実際のサーバーそのものを管理できます。 Skype ビジネス サーバー管理シェルを使用してこれらの設定を設定できます。
  
ビジネス サーバーの Skype をインストールするときにシステムで会議の単一のコレクション (グローバル コレクション) の構成設定。 サイトまたはサービス用のカスタム設定を作成する場合は、**新規 CsConferencingConfiguration**コマンドレットを使用してこれを行うことができます。 サイトまたはサービス スコープでのみ新しい設定を適用できることに注意してください。構成の設定、会議の新しいグローバル コレクションを作成できませんが、**セット CsConferencingConfiguration**コマンドレットを使用してグローバル コレクションを変更することができます。 さらに、サイトまたはサービスをホストできますなしの設定の 1 つ以上のコレクションです。 しようとするとサイトと、レドモンドは、レドモンドの新しい設定を作成するサイトは既にホスト会議構成設定のコレクションから、コマンドは失敗します。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>ビジネス サーバー管理シェルの Skype を使用して、会議構成設定を管理します。

Skype ビジネス サーバー管理シェルを使用して会議の構成の設定を管理するには、次のコマンドレットを使用します。
  
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
  

