---
title: Microsoft Teams のセキュリティ ガイド
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 職場の共有コンピューターから Microsoft Teams を安全に使用するためのガイダンス。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45497c824cfc20644a59e35f7812b17058f61c2c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117055"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>共有コンピューターで Microsoft Teams を安全に使用する

可能な場合は、クライアントデバイスに対して、デバイス管理機能、デバイスのヘルスチェックとポリシーの実施、デバイスレベルの暗号化、およびその他のセキュリティ機能を利用したゼロトラストアプローチを利用することを *お勧め* します。

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="ゼロトラストの写真は、青い円によって、明示的に確認し、最小限の特権しか与えず、違反を常に想定するというゼロトラストの中心原則を示しています。":::

管理者は、検証と最小限の特権を *主張* し、妥協案を想定することで、ユーザーとデータの両方に対するリスクを最小限に抑えるアクションにつながる標準を使用して、非常に安全な条件を作成できます。

> [!TIP]
> ゼロトラストの原則の詳細については、[こちらのビデオ](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537)を参照してください。

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>共有コンピューターから Microsoft Teams を安全に使用するためのヒント

すべての状況で可能ではない、または実用的とは限りませんが、それでも、セキュリティ管理者が共有コンピューターまたは管理対象外のデバイスから Teams を使用するためのガイダンスに可能な限り従うことは重要です。

可能な限り迅速にガイドラインに準拠するように計画を策定する必要があります。

1. オペレーティングシステムプラットフォームのセキュリティ機能を利用します。
    1. オペレーティングシステムがオペレーティングシステムプロバイダーからの自動更新をインストールするように構成されていることを確認します（Microsoft システムの場合、これは [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq) から実行できます）。 
    1. [**BitLocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) などのデバイスの暗号化機能が有効になっており、デバイスへのアクセスに使用するキーが保護されていることを確認します。  最近のほとんどの [**Windows 10 デバイスはbitlockerをサポートしています**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)。 
    1. デバイスで、[**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) が提供するようなウイルス対策機能を使用します。
    1. システムのユーザーごとに[個別のユーザーアカウント](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)を使用することを強くお勧めします。
    1. 管理権限を必要としない機能（Web の閲覧、Teams の実行など）に対して管理者権限を付与または使用 *しない* でください。

上記のガイダンスが満たされていない場合は、追加のブラウザーセキュリティのベストプラクティスを利用することをお勧めします。

1. ブラウザのセキュリティ機能を活用します。
    1. プライベートブラウズセッションを使用して、ディスクに残るデータや履歴を最小限に抑えます。 たとえば、[Microsoft Edge での inPrivate ブラウズ](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate)、[Google Chrome でのシークレットブラウズ](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)、または特定のブラウザでのプライベートブラウズ機能を使用します。 
    1. *既定で* プライベートブラウズを行うようにシステムの動作を変更しておくことをお勧めします。 

2. ダウンロード可能な Teams クライアントではなく、[Teams Web アプリ](https://teams.microsoft.com)（*Web* クライアントとも呼ばれます）を閲覧して使用します。

3. 共有システムの使用が終了したら、次のことを行う必要があります。 
    1. [Teams からサインアウトする](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487)。
    1. ブラウザーのすべてのタブおよびウィンドウを閉じる。
    1. デバイスからサインアウトする。

上記の項目は、すべてのケースを網羅するベストプラクティスまたはセキュリティ管理の包括的なリストではなく、環境内で実行できる追加のアクションがある場合があります（たとえば、[Office 365 ATP プラン 1 または 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) を使用している場合、セキュリティ管理者は Teams のセーフリンクとセーフアタッチメントの使用を選択できます）。 ただし、これらの手順は、共有デバイスから Teams を使用するためのガイダンスを構築するための開始点です。

## <a name="more-information"></a>詳細

[構成マネージャーの Bitlocker](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[Intune の Windows 10 用 Bitlocker](/mem/intune/protect/encrypt-devices)

[Intune のエンドポイントセキュリティ](/mem/intune/protect/endpoint-security)

Windows セキュリティで Microsoft Defender Antivirus を[有効](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app)にして[スキャンを実行する](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Microsoft Defender セキュリティセンターの記事](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Tems Web クライアント/ Teams Web アプリ](./get-clients.md#web-client)

[セキュリティと Microsoft Teams](./teams-security-guide.md)