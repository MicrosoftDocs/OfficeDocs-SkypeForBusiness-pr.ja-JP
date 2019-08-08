---
title: オンプレミスの Skype for Business Server と Outlook Web App との統合を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '概要: Skype for Business Server と Outlook Web App の統合。'
ms.openlocfilehash: b7c279dc41515d9613d8c000ab9e81164a1ccaa6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244211"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>オンプレミスの Skype for Business Server と Outlook Web App との統合を構成する

**概要:** Skype for Business Server と Outlook Web App を統合します。

オンプレミスの Skype for Business Server 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Exchange Online の Microsoft Outlook Web App との相互運用性を構成できます。 相互運用性機能には、シングル サインオンが含まれるほか、Outlook Web App インターフェイスとのインスタント メッセージングおよびプレゼンスの統合が含まれます。 この統合を有効にするには、次のタスクを実行して、オンプレミスの Skype for Business Server 展開でエッジサーバーを構成する必要があります。

- 共有 SIP アドレス スペースを構成する

- エッジサーバーでホスティングプロバイダーを構成する

- 更新された中央管理ストアのレプリケーションを確認する

## <a name="configure-a-shared-sip-address-space"></a>共有 SIP アドレス スペースを構成する

オンプレミスの Skype for Business Server を Exchange Online と統合するには、共有 SIP アドレス空間を構成する必要があります。 同じ SIP ドメインアドレス空間は、Skype for Business Server と Exchange Online サービスの両方でサポートされています。

次の例に示すパラメーターを使用して、 **CSAccessEdgeConfiguration**コマンドレットを実行して、Skype For Business Server 管理シェルを使ってフェデレーション用にエッジサーバーを構成します。

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** パラメーターは、内部ユーザーがフェデレーション ドメインからのユーザーと通信することを許可するかどうかを指定します。 このプロパティは、Skype for Business Server および Exchange Online で、内部ユーザーが共有 SIP アドレス空間のシナリオでユーザーと通信できるかどうかも決定します。

Skype for Business Server 管理シェルの使い方の詳細については、「Skype for business [Server 管理シェル](../../manage/management-shell.md)」を参照してください。

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>エッジ サーバーにホスティング プロバイダーを構成する

Skype for Business Server 管理シェルを使用して、次の例のパラメーターを使用して、**新しい-CsHostingProvider**コマンドレットを実行して、エッジサーバーでホスティングプロバイダーを構成します。

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 中国の 21Vianet により運営されている Office 365 を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を、21Vianet により運営されているサービスの FQDN である "exap.um.partner.outlook.cn" に置き換えます。 Office 365 GCC High を使用している場合は、この例の ProxyFqdn パラメーター ("exap.um.outlook.com") の値を、GCC High: "exap.um.office365.us" の FQDN に置き換えます。

- **Identity** は、作成するホスティング プロバイダーの、一意の文字列値から成る識別子を指定します (例: "Exchange Online")。 空白を含む値は、二重引用符で囲む必要があります。

- **Enabled ** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 これを True に設定する必要があります。

- **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 これを True に設定する必要があります。

- **Hostているユーザー**は、ホスティングプロバイダーが Office Communications server または Skype For business Server をホストするために使用されているかどうかを示します。 これを False に設定する必要があります。

- **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 Exchange Online の FQDN は exap.um.outlook.com です。

- **Islocal**は、ホスティングプロバイダーによって使用されたプロキシサーバーが Skype For business server トポロジ内に含まれているかどうかを示します。 これを False に設定する必要があります。

- **VerificationLevel**ホストされているプロバイダーとの間で送受信されるメッセージに対して許可される確認レベルを示します。 ホスティング**** プロバイダーから送信されたメッセージに含まれている確認レベルに依存する、"いいね" を指定します。 このレベルが指定されていない場合、メッセージは、確認不能として拒否されます。

## <a name="verify-replication-of-the-updated-central-management-store"></a>更新された中央管理ストアのレプリケーションを確認する

前のセクションのコマンドレットを使用して行った変更は、エッジサーバーに自動的に適用され、通常、複製には1分未満かかります。 レプリケーションの状態を確認し、次のコマンドレットを使用して、変更がエッジサーバーに適用されたことを確認できます。

レプリケーションの更新を確認するには、Skype for Business Server の展開の内部サーバーで、次のコマンドレットを実行します。

```
Get-CsManagementStoreReplicationStatus
```
UpToDate 値がすべてのレプリカの TRUE として表示されているかどうかを確認します。

変更が適用されたことを確認するには、エッジサーバーで次のコマンドレットを実行します。

```
Get-CsHostingProvider -LocalStore
```
表示されている情報が、前の手順でコミットした変更内容と一致するかどうかをダブルチェックします。

## <a name="see-also"></a>関連項目

[ホストされている Exchange UM での Skype for Business Server ユーザーのボイスメールの提供](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Skype for Business Server でのホストされた Exchange ユニファイドメッセージングの統合](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
