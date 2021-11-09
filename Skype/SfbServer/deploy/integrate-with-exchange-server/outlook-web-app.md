---
title: オンプレミスのサーバーとサーバー間の統合Skype for Business Server構成Outlook Web App
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '概要: 統合Skype for Business ServerとOutlook Web App。'
ms.openlocfilehash: cebb8fed6b87dac6ec2c981730d303994c952741
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853681"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>オンプレミスのサーバーとサーバー間の統合Skype for Business Server構成Outlook Web App

**概要:** 統合Skype for Business ServerとOutlook Web App。

オンプレミスの展開を使用しているSkype for Business Server、ハイブリッド展開モードでMicrosoft Outlook Web App Microsoft Exchange Online相互運用性を構成できます。 相互運用性機能には、シングル サインオンとインスタント メッセージング (IM) とプレゼンスの統合が含まれます。Outlook Web Appです。 この統合を有効にするには、次のタスクを実行して、オンプレミスのサーバー Skype for Business Serverエッジ サーバーを構成する必要があります。

- 共有 SIP アドレス空間を構成する

- エッジ サーバーでホスティング プロバイダーを構成する

- 更新されたサーバーの全体管理ストアのレプリケーションを確認する

## <a name="configure-a-shared-sip-address-space"></a>共有 SIP アドレス空間の構成

オンプレミス のデバイスを Skype for Business ServerとExchange Online、共有 SIP アドレス空間を構成する必要があります。 同じ SIP ドメイン アドレス空間は、サービスとサービスSkype for Business ServerでExchange Onlineされます。

Skype for Business Server管理シェルを使用して、次の例に示すパラメーターを使用して **Set-CSAccessEdgeConfiguration** コマンドレットを実行して、フェデレーション用にエッジ サーバーを構成します。

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** パラメーターは、内部ユーザーがフェデレーション ドメインのユーザーと通信できるかどうかを指定します。 また、このプロパティは、内部ユーザーが共有 SIP アドレス空間シナリオでユーザーと通信できるかどうかをSkype for Business ServerおよびExchange Online。

管理シェルの使用のSkype for Business Server詳細については、「管理シェルSkype for Business Server[を参照してください](../../manage/management-shell.md)。

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>エッジ サーバーでホスティング プロバイダーを構成する

Skype for Business Server管理シェルを使用して、次の例のパラメーターを使用して **、New-CsHostingProvider** コマンドレットを実行してエッジ サーバー上でホスティング プロバイダーを構成します。

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 中国で 21Vianet が運用する Microsoft 365 または Office 365 を使用している場合は、この例 ("exap.um.outlook.com") の ProxyFqdn パラメーターの値を、21Vianet が運用するサービスの FQDN "exap.um.partner.outlook.cn" に置き換えてください。 Microsoft 365 または Office 365 GCC High を使用している場合は、この例 ("exap.um.outlook.com") の ProxyFqdn パラメーターの値を、GCC High: "exap.um.office365.us" の FQDN に置き換えてください。

- **Identity** は、作成するホスティング プロバイダーの一意の文字列値識別子を指定します (たとえば、"Exchange Online")。 スペースを含む値は二重引用符で囲む必要があります。

- **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 これは True に設定する必要があります。

- **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 これは True に設定する必要があります。

- **HostsOCSUsers は**、ホスティング プロバイダーを使用して通信サーバーまたはサーバーをホストOfficeをSkype for Business Server。 これは False に設定する必要があります。

- **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 たとえばExchange Online FQDN は exap.um.outlook.com。

- **IsLocal は**、ホスティング プロバイダーによって使用されるプロキシ サーバーが、ホスト トポロジ内に含まれているSkype for Business Serverします。 これは False に設定する必要があります。

- **VerificationLevel** ホストされているプロバイダーとの間で送信されるメッセージに対して許可される検証レベルを示します。 ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。 このレベルを指定しない場合、メッセージは確認できないとして拒否されます。

## <a name="verify-replication-of-the-updated-central-management-store"></a>更新された中央管理ストアのレプリケーションを確認する

前のセクションのコマンドレットを使用して行った変更は、エッジ サーバーに自動的に適用され、一般にレプリケートに 1 分未満かかっています。 レプリケーションの状態を検証し、次のコマンドレットを使用して、エッジ サーバーに変更が適用されたと確認できます。

レプリケーションの更新を確認するには、サーバーの展開内Skype for Business Server、次のコマンドレットを実行します。

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

[ホストSkype for Business Server UM でユーザーにボイス メールExchangeする](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[ホストExchangeユニファイド メッセージングの統合 (Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)