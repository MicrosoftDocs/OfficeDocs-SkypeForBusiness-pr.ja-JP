---
title: ビジネス サーバーの設置型の Skype と Outlook Web App との統合を構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '概要: ビジネス サーバーおよび Outlook Web App の Skype を統合します。'
ms.openlocfilehash: 5ad1f6bc898a29c2a5e0f326d3a5edc4d782bab2
ms.sourcegitcommit: 25066ab000f7615aff31f77d9d39c266c65e2aa5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2018
ms.locfileid: "22914097"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>ビジネス サーバーの設置型の Skype と Outlook Web App との統合を構成します。
 
**の概要:** ビジネス サーバーおよび Outlook Web App には、Skype を統合します。
  
ビジネス サーバー展開では、オンプレミスの Skype を使用しているお客様は、ハイブリッド展開モードで、Microsoft Exchange Online での Microsoft Outlook Web App での相互運用性を構成できます。 相互運用性機能には、シングル サインオンが含まれるほか、Outlook Web App インターフェイスとのインスタント メッセージングおよびプレゼンスの統合が含まれます。 この統合を有効にするには、次のタスクを完了して、設置の Skype ビジネス サーバーの展開にエッジ サーバーを構成する必要があります。 
  
- 共有 SIP アドレス スペースを構成する
    
- エッジ サーバー上でホスティング プロバイダーを構成します。
    
- 更新された中央管理ストアのレプリケーションを確認します。
    
## <a name="configure-a-shared-sip-address-space"></a>共有 SIP アドレス スペースを構成する

Exchange のオンラインでのビジネスのサーバーの設置型の Skype を統合するために共有 SIP アドレス スペースを構成する必要があります。 同じ SIP ドメインのアドレス スペースは、Skype のビジネス サーバーと Exchange のオンライン サービスの両方でサポートされています。
  
ビジネス サーバー管理シェルには、Skype を使用して、次の例に表示されているパラメーターを使用して、**セット CSAccessEdgeConfiguration**コマンドレットを実行して、エッジ サーバーのフェデレーションを構成します。
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers**パラメーターは、内部ユーザーがフェデレーション ドメインのユーザーと通信できるかどうかを指定します。 このプロパティは、内部ユーザーが、ビジネスのサーバーと Exchange のオンライン共有 SIP アドレス スペースのシナリオで Skype でのユーザーと通信できるかどうかも決定します。
    
ビジネス サーバー管理シェルには、Skype の使用に関する詳細については、 [Skype](../../manage/management-shell.md)ビジネス サーバー管理シェルを参照してください。
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a>エッジ サーバーにホスティング プロバイダーを構成する

ビジネス サーバー管理シェルには、Skype を使用して、次の例では、パラメーターを使用して、**新規 CsHostingProvider**コマンドレットを実行してエッジ サーバー上でホスティング プロバイダーを構成します。
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 中国の 21Vianet により運営されている Office 365 を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を、21Vianet により運営されているサービスの FQDN である "exap.um.partner.outlook.cn" に置き換えます。 を使用している Office 365 の GCC の高い場合、FQDN を持つ次の使用例がある場合 ("exap.um.outlook.com") で ProxyFqdn パラメーターの値を交換して、GCC を:"exap.um.office365.us"です。
  
- **アイデンティティ**では、(たとえば、Exchange オンライン) を作成するホスティング プロバイダーの一意の文字列値の識別子を指定します。 空白を含む値は、二重引用符で囲む必要があります。
    
- **Enabled ** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 これを True に設定する必要があります。
    
- **EnabledSharedAddressSpace**では、ホスティング プロバイダーが共有 SIP アドレス スペースのシナリオで使用するかどうかを示します。 これを True に設定する必要があります。
    
- **HostsOCSUsers**は、Office Communications Server または Skype をビジネスのサーバーのホストにホスティング プロバイダーを使用するかどうかを示します。 これを False に設定する必要があります。
    
- **ProxyFQDN**は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 Exchange Online の FQDN は exap.um.outlook.com です。
    
- **IsLocal**は、ビジネスのサーバー トポロジの場合、Skype 内でホスティング プロバイダーで使用するプロキシ サーバーが含まれているかどうかを示します。 これを False に設定する必要があります。
    
- **VerificationLevel**ホストされるプロバイダーとの間に送信できるメッセージの確認レベルを示します。 **UseSourceVerification**、ホスティング プロバイダーから送信されたメッセージに含まれている検証のレベルに依存する部分を指定します。 このレベルが指定されていない場合、メッセージは、確認不能として拒否されます。
    
## <a name="verify-replication-of-the-updated-central-management-store"></a>更新された中央管理ストアのレプリケーションを確認する

コマンドレットを使用して、前のセクションで、加えた変更は、エッジ サーバーに自動的に適用し、を複製するのには 1 分未満がかかります。 レプリケーションの状態を検証し、次のコマンドレットを使用して、エッジ サーバーに変更が適用されたことを確認できます。
  
ビジネス サーバーの展開、Skype の内部のサーバー上のレプリケーションの更新を確認するには、次のコマンドレットを実行します。
  
```
Get-CsManagementStoreReplicationStatus
```

エッジ サーバーで、変更が適用されたことを確認するには、次のコマンドレットを実行します。
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a>関連項目

[Skype を提供するビジネスのサーバーのユーザーのボイス メールでホストされている Exchange UM](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[ホストされている Exchange ユニファイド メッセージング統合の Skype ビジネス サーバーの](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)