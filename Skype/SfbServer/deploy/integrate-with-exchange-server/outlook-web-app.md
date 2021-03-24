---
title: オンプレミスの Skype for Business Server とサーバー間の統合を構成Outlook Web App
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
description: '概要: Skype for Business Server とビジネス サーバーを統合Outlook Web App。'
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109693"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>オンプレミスの Skype for Business Server とサーバー間の統合を構成Outlook Web App

**概要:** Skype for Business Server とビジネス サーバーを統合Outlook Web App。

オンプレミスの Skype for Business Server 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Outlook Web App Microsoft Exchange Online相互運用性を構成できます。 相互運用性の機能には、シングル サインオンとインスタント メッセージング (IM) とプレゼンスの統合が含Outlook Web Appがあります。 この統合を有効にするには、次のタスクを実行して、オンプレミスの Skype for Business Server 展開でエッジ サーバーを構成する必要があります。

- 共有 SIP アドレス空間を構成する

- エッジ サーバーでホスティング プロバイダーを構成する

- 更新されたサーバーの全体管理ストアのレプリケーションを確認する

## <a name="configure-a-shared-sip-address-space"></a>共有 SIP アドレス空間の構成

オンプレミスの Skype for Business Server を Exchange Online と統合するには、共有 SIP アドレス空間を構成する必要があります。 同じ SIP ドメイン アドレス空間は、Skype for Business Server と Exchange Online サービスの両方でサポートされます。

Skype for Business Server 管理シェルを使用して、次の例に示すパラメーターを使用して **Set-CSAccessEdgeConfiguration** コマンドレットを実行して、フェデレーション用にエッジ サーバーを構成します。

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** パラメーターは、内部ユーザーがフェデレーション ドメインのユーザーと通信できるかどうかを指定します。 このプロパティは、内部ユーザーが Skype for Business Server および Exchange Online との共有 SIP アドレス空間シナリオでユーザーと通信できるかどうかも決定します。

Skype for Business Server 管理シェルの使用の詳細については [、「Skype for Business Server Management Shell」を参照してください](../../manage/management-shell.md)。

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>エッジ サーバーでホスティング プロバイダーを構成する

Skype for Business Server 管理シェルを使用して、次の例のパラメーターを使用して **、New-CsHostingProvider** コマンドレットを実行してエッジ サーバー上のホスティング プロバイダーを構成します。

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 中国で 21Vianet が運用する Microsoft 365 または Office 365 を使用している場合は、この例 ("exap.um.outlook.com") の ProxyFqdn パラメーターの値を、21Vianet が運用するサービスの FQDN に置き換えてください。"exap.um.partner.outlook.cn"。 Microsoft 365 または Office 365 GCC High を使用している場合は、この例 ("exap.um.outlook.com") の ProxyFqdn パラメーターの値を GCC High の FQDN "exap.um.office365.us" に置き換えてください。

- **Identity** は、作成するホスティング プロバイダーの一意の文字列値識別子を指定します (たとえば、"Exchange Online")。 スペースを含む値は二重引用符で囲む必要があります。

- **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 これは True に設定する必要があります。

- **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 これは True に設定する必要があります。

- **HostsOCSUsers は** 、ホスティング プロバイダーを使用して通信サーバーまたは Skype for Business Server Officeホストするかどうかを示します。 これは False に設定する必要があります。

- **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 Exchange Online の場合、FQDN は exap.um.outlook.com。

- **IsLocal は** 、ホスティング プロバイダーによって使用されるプロキシ サーバーが Skype for Business Server トポロジ内に含まれているかどうかを示します。 これは False に設定する必要があります。

- **VerificationLevel** ホストされているプロバイダーとの間で送信されるメッセージに対して許可される検証レベルを示します。 ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。 このレベルを指定しない場合、メッセージは確認できないとして拒否されます。

## <a name="verify-replication-of-the-updated-central-management-store"></a>更新された中央管理ストアのレプリケーションを確認する

前のセクションのコマンドレットを使用して行った変更は、エッジ サーバーに自動的に適用され、一般にレプリケートに 1 分未満かかっています。 レプリケーションの状態を検証し、次のコマンドレットを使用して、エッジ サーバーに変更が適用されたと確認できます。

レプリケーションの更新を確認するには、Skype for Business Server 展開の内部サーバーで、次のコマンドレットを実行します。

```powershell
Get-CsManagementStoreReplicationStatus
```
すべてのレプリカに対して UpToDate 値が TRUE を表示している場合に確認します。

変更が適用されたと確認するには、エッジ サーバーで次のコマンドレットを実行します。

```powershell
Get-CsHostingProvider -LocalStore
```
表示される情報が、前の手順でコミットされた変更と一致する場合は、ダブル チェックします。

## <a name="see-also"></a>関連項目

[ホストされている Exchange UM での Skype for Business Server ユーザーのボイス メールの提供](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[Skype for Business Server でのホストされた Exchange ユニファイド メッセージングの統合](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)