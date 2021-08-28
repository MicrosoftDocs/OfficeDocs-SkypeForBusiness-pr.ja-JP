---
title: ドメイン内のレプリケーションの確認
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: '「手順 1: スキーマの準備」で実行したドメイン準備のレプリケーションを確認するには、Skype for Business Server 管理シェル Lync Server 管理シェルからコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、準備したドメインのメンバーであるコンピューターに Domain Admins グループのメンバーとしてログオンします。 次の操作を行ってください。'
ms.openlocfilehash: e3c4a1d234427c43a9b0de298591b08f8a8194df
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591821"
---
# <a name="verify-replication-in-the-domain"></a>ドメイン内のレプリケーションの確認
 
「手順 **1:** スキーマの準備」で実行したドメイン準備のレプリケーションを確認するには、Skype for Business Server 管理シェル Lync Server 管理シェルからコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、準備したドメインのメンバーであるコンピューターに Domain Admins グループのメンバーとしてログオンします。 次の操作を行ってください。
  
1. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. [Windows PowerShell] に、次の値を入力します。
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    次に例を示します。
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。 設定が System コンテナーに格納されている場合 (グローバル設定が構成コンテナーに移行されていないアップグレード展開では一般的です)、Active Directory ドメイン サービス フォレストのルートにドメイン コントローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、コマンドレットは設定が構成コンテナーに格納され、Active Directory の任意のドメイン コントローラーを参照すると想定します。 
  
    Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。ドメインの準備が成功した場合、このコマンドレットを実行すると、値 **LC_DOMAIN_SETTINGS_STATE_READY** が戻されます。
    

