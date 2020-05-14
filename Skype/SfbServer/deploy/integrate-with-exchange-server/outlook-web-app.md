---
title: オンプレミスの Skype for Business Server と Outlook Web App 間の統合を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '概要: Skype for Business Server と Outlook Web App を統合します。'
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221187"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>オンプレミスの Skype for Business Server と Outlook Web App 間の統合を構成する

**概要:** Skype for Business Server と Outlook Web App を統合します。

オンプレミスの Skype for Business Server 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Exchange Online の Microsoft Outlook Web App との相互運用性を構成できます。 相互運用性機能には、Outlook Web App インターフェイスとのシングルサインオン、インスタントメッセージング (IM)、プレゼンス統合が含まれます。 この統合を有効にするには、次のタスクを完了して、オンプレミスの Skype for Business Server 展開でエッジサーバーを構成する必要があります。

- 共有 SIP アドレススペースを構成する

- エッジサーバーのホスティングプロバイダーを構成する

- 更新された中央管理ストアのレプリケーションを確認する

## <a name="configure-a-shared-sip-address-space"></a>共有 SIP アドレススペースを構成する

オンプレミスの Skype for Business Server を Exchange Online と統合するには、共有 SIP アドレススペースを構成する必要があります。 同じ SIP ドメインアドレススペースが、Skype for Business Server と Exchange Online サービスの両方でサポートされています。

Skype for Business Server 管理シェルを使用して、次の例に示されているパラメーターを使用して**set-csaccessedgeconfiguration**コマンドレットを実行し、フェデレーション用にエッジサーバーを構成します。

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers**パラメーターは、内部ユーザーがフェデレーションドメインからのユーザーと通信できるかどうかを指定します。 このプロパティは、内部ユーザーが Skype for Business Server と Exchange Online を使用して、共有 SIP アドレススペースシナリオのユーザーと通信できるかどうかも決定します。

Skype for business Server 管理シェルの使用の詳細については、「 [skype for Business Server Management shell](../../manage/management-shell.md)」を参照してください。

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>エッジサーバーのホスティングプロバイダーを構成する

Skype for Business Server 管理シェルを使用して、次の例のパラメーターを使用して、**新しい-CsHostingProvider**コマンドレットを実行して、エッジサーバーのホスティングプロバイダーを構成します。

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 中国で21Vianet が運用している Microsoft 365 または Office 365 を使用している場合は、この例の ProxyFqdn パラメーター ("exap.um.outlook.com") の値を、21Vianet が運用しているサービスの FQDN に置き換えます。 "exap.um.partner.outlook.cn"。 Microsoft 365 または Office 365 GCC High を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を、GCC High: "exap.um.office365.us" の FQDN に置き換えます。

- **Identity**は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します (例: "Exchange Online")。 スペースを含む値は、二重引用符で囲む必要があります。

- **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 True に設定する必要があります。

- **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 True に設定する必要があります。

- **Hostソケット Susers**は、ホスティングプロバイダーが Office Communications server または Skype For business server をホストするために使用されているかどうかを示します。 この値は False に設定する必要があります。

- **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 Exchange Online の場合、FQDN は exap.um.outlook.com です。

- **Islocal**は、ホスティングプロバイダーによって使用されるプロキシサーバーが Skype For business server のトポロジ内に含まれているかどうかを示します。 この値は False に設定する必要があります。

- **VerificationLevel**ホストされているプロバイダーとの間で送受信されるメッセージに対して許可される検証レベルを示します。 ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。 このレベルが指定されていない場合、メッセージは検証不能として拒否されます。

## <a name="verify-replication-of-the-updated-central-management-store"></a>更新された中央管理ストアのレプリケーションを確認する

前のセクションのコマンドレットを使用して行った変更は、エッジサーバーに自動的に適用され、通常、レプリケートするのに1分未満になります。 次のコマンドレットを使用して、レプリケーションの状態を検証し、変更がエッジサーバーに適用されたことを確認できます。

レプリケーションの更新を確認するには、Skype for Business Server 展開の内部サーバーで、次のコマンドレットを実行します。

```powershell
Get-CsManagementStoreReplicationStatus
```
UpToDate value がすべてのレプリカに対して TRUE を示しているかどうかを確認します。

変更が適用されたことを確認するには、エッジサーバーで次のコマンドレットを実行します。

```powershell
Get-CsHostingProvider -LocalStore
```
表示されている情報が、前の手順で確定した変更内容と一致しているかどうかを確認します。

## <a name="see-also"></a>関連項目

[ホストされた Exchange UM で Skype for Business Server ユーザーにボイスメールを提供する](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Skype for Business Server でのホスト型 Exchange ユニファイドメッセージングの統合](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
