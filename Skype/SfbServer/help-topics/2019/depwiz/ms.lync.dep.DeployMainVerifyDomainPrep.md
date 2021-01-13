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
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: '「手順 1: スキーマを準備する」で実行したドメイン準備のレプリケーションを確認するには、Skype for Business Server 管理シェル Lync Server 管理シェルからコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、準備したドメインのメンバーであるコンピューターに Domain Admins グループのメンバーとしてログオンします。 次の操作を行ってください。'
ms.openlocfilehash: 9ec39551702e0f3480671787536929863cb61f6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801657"
---
# <a name="verify-replication-in-the-domain"></a>ドメイン内のレプリケーションの確認
 
「手順 **1:** スキーマを準備する」で実行したドメイン準備のレプリケーションを確認するには、Skype for Business Server 管理シェル Lync Server 管理シェルからコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、準備したドメインのメンバーであるコンピューターに Domain Admins グループのメンバーとしてログオンします。 次の操作を行ってください。
  
1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
2. 次Windows PowerShell入力します。
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    次に例を示します。
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。 設定がシステム コンテナーに格納されている場合 (グローバル設定が構成コンテナーに移行されていないアップグレード展開で一般的)、Active Directory ドメイン サービス フォレストのルートにドメイン コントローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、コマンドレットは設定が構成コンテナーに格納され、Active Directory 内の任意のドメイン コントローラーを参照すると想定します。 
  
    Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。 ドメインの準備が成功した場合、このコマンドレットを実行すると、値 **LC_DOMAIN_SETTINGS_STATE_READY** が戻されます。
    

