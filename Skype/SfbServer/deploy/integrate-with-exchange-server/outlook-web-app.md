---
title: オンプレミスの Skype for Business Server と組織の間の統合をOutlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server と Outlook Web App。'
ms.openlocfilehash: 0a6358c93356bd059aeed34033b07916d856bf10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833967"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>オンプレミスの Skype for Business Server と組織の間の統合をOutlook Web App

**概要:** Skype for Business Server と Outlook Web App。

オンプレミスの Skype for Business Server 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Outlook Web App Microsoft Exchange Online相互運用性を構成できます。 相互運用性機能には、シングル サインオンとインスタント メッセージング (IM) とプレゼンスの統合が含Outlook Web Appがあります。 この統合を有効にするには、次のタスクを実行して、オンプレミスの Skype for Business Server 展開でエッジ サーバーを構成する必要があります。

- 共有 SIP アドレス スペースを構成する

- エッジ サーバーでホスティング プロバイダーを構成する

- 更新された中央管理ストアのレプリケーションを確認する

## <a name="configure-a-shared-sip-address-space"></a>共有 SIP アドレス スペースを構成する

オンプレミスの Skype for Business Server を Exchange Online と統合するには、共有 SIP アドレス スペースを構成する必要があります。 同じ SIP ドメイン アドレス スペースは、Skype for Business Server と Exchange Online サービスの両方でサポートされています。

Skype for Business Server 管理シェルを使用して、次の例に示すパラメーターを使用して **Set-CSAccessEdgeConfiguration** コマンドレットを実行して、フェデレーション用にエッジ サーバーを構成します。

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** パラメーターは、内部ユーザーがフェデレーション ドメインのユーザーと通信できるかどうかを指定します。 また、このプロパティは、内部ユーザーが Skype for Business Server および Exchange Online との共有 SIP アドレス スペース シナリオでユーザーと通信できるかどうかも決定します。

Skype for Business Server 管理シェルの使用の詳細については [、「Skype for Business Server Management Shell」を参照してください](../../manage/management-shell.md)。

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>エッジ サーバーでホスティング プロバイダーを構成する

Skype for Business Server 管理シェルを使用して、次の例のパラメーターを使用して **New-CsHostingProvider** コマンドレットを実行して、エッジ サーバーでホスティング プロバイダーを構成します。

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 中国の 21Vianet が運用している Microsoft 365 または Office 365 を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を、21Vianet が運用しているサービスの FQDN ("exap.um.partner.outlook.cn") に置き換えてください。 Microsoft 365 または Office 365 GCC High を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を GCC High : "exap.um.office365.us" の FQDN に置き換えてください。

- **Identity** は、作成するホスティング プロバイダーの一意の文字列値識別子を指定します (例: "Exchange Online")。 スペースを含む値は二重引用符で囲む必要があります。

- **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 True に設定する必要があります。

- **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 True に設定する必要があります。

- **HostsOCSUsers は** 、ホスティング プロバイダーが Communications Server または Skype for Business Server のOfficeに使用されるかどうかを示します。 これは False に設定する必要があります。

- **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 Exchange Online の場合、FQDN はexap.um.outlook.com。

- **IsLocal** は、ホスティング プロバイダーによって使用されるプロキシ サーバーが Skype for Business Server トポロジ内に含まれているかどうかを示します。 これは False に設定する必要があります。

- **VerificationLevel** ホストされるプロバイダーとの間で送信されるメッセージに対して許可される検証レベルを示します。 ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。 このレベルを指定しない場合、メッセージは確認不可として拒否されます。

## <a name="verify-replication-of-the-updated-central-management-store"></a>更新された中央管理ストアのレプリケーションを確認する

前のセクションのコマンドレットを使用して行った変更は、エッジ サーバーに自動的に適用され、通常、レプリケートに 1 分未満かかっています。 次のコマンドレットを使用して、レプリケーションの状態を検証し、変更がエッジ サーバーに適用されたのを確認できます。

レプリケーションの更新を確認するには、Skype for Business Server 展開の内部サーバーで、次のコマンドレットを実行します。

```powershell
Get-CsManagementStoreReplicationStatus
```
UpToDate の値がすべてのレプリカに対して TRUE と表示されるのを確認します。

変更が適用されたのを確認するには、エッジ サーバーで次のコマンドレットを実行します。

```powershell
Get-CsHostingProvider -LocalStore
```
表示される情報が前の手順でコミットされた変更と一致する場合は、ダブル チェックします。

## <a name="see-also"></a>関連項目

[Hosted Exchange UM で Skype for Business Server ユーザーにボイス メールを提供する](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Skype for Business Server での Hosted Exchange ユニファイド メッセージングの統合](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
