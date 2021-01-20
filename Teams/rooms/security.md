---
title: Microsoft Teams の会議室のセキュリティ
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Microsoft Teams Rooms デバイスをセキュリティで保護する方法について説明します。
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880881"
---
# <a name="microsoft-teams-rooms-security"></a><span data-ttu-id="9885a-103">Microsoft Teams の会議室のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="9885a-103">Microsoft Teams Rooms Security</span></span>

<span data-ttu-id="9885a-104">Microsoft はパートナーと協力して、セキュリティで保護されたソリューションを提供し、Microsoft Teams Rooms をセキュリティで保護するために追加のアクションを必要としない。</span><span class="sxs-lookup"><span data-stu-id="9885a-104">Microsoft works with our partners to deliver a solution that is secure and doesn't require additional actions to secure Microsoft Teams Rooms.</span></span> <span data-ttu-id="9885a-105">この記事では、Teams Rooms のセキュリティ機能の多くについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9885a-105">This article discusses many of the security features found in Teams Rooms.</span></span>

> [!NOTE]
> <span data-ttu-id="9885a-106">Microsoft Teams の会議室は、一般的なエンド ユーザー ワークステーションと同様に扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-106">Microsoft Teams Rooms should not be treated like a typical end-user workstation.</span></span> <span data-ttu-id="9885a-107">使用例が大幅に異なるだけでなく、既定のセキュリティ プロファイルも大幅に異なります。</span><span class="sxs-lookup"><span data-stu-id="9885a-107">Not only are the use cases vastly different, but the default security profiles are also much different.</span></span>

<span data-ttu-id="9885a-108">制限されたエンド ユーザー データは、Teams の会議室に保存されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-108">Limited end-user data is stored on Teams Rooms.</span></span> <span data-ttu-id="9885a-109">エンドユーザー データは、トラブルシューティングとサポートのみを行うログ ファイルに保存される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-109">End-user data may be stored in the log files for troubleshooting and support only.</span></span> <span data-ttu-id="9885a-110">Teams Rooms を使用する会議の出席者は、ファイルをハード ドライブにコピーしたり、自分自身でサインインしたりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9885a-110">At no point can an attendee of a meeting using Teams Rooms copy files to the hard drive or sign in as themselves.</span></span> <span data-ttu-id="9885a-111">Microsoft Teams Rooms デバイスにエンドユーザー データを転送したり、アクセスしたりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9885a-111">No end-user data is transferred to, or accessible by, the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="9885a-112">エンド ユーザーが Teams Rooms のハード ドライブにファイルを保存することはできませんが、Microsoft Defender は引き続き有効です。</span><span class="sxs-lookup"><span data-stu-id="9885a-112">Even though end users can't put files on a Teams Rooms hard drive, Microsoft Defender is still enabled.</span></span> <span data-ttu-id="9885a-113">Teams Rooms のパフォーマンスは Microsoft Defender でテストされます。</span><span class="sxs-lookup"><span data-stu-id="9885a-113">Teams Rooms performance is tested with Microsoft Defender.</span></span> <span data-ttu-id="9885a-114">これを無効にするか、エンドポイント セキュリティ ソフトウェアを追加すると、予期しない結果が生じ、システムが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-114">Disabling this or adding endpoint security software can lead to unpredictable results and potential system degradation.</span></span>

## <a name="hardware-security"></a><span data-ttu-id="9885a-115">ハードウェアのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="9885a-115">Hardware security</span></span>

<span data-ttu-id="9885a-116">Teams Rooms 環境には、Windows 10 IoT Enterprise エディションを実行する中央演算モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="9885a-116">In a Teams Rooms environment, there's a central compute module that runs Windows 10 IoT Enterprise edition.</span></span> <span data-ttu-id="9885a-117">認証済みのすべての計算モジュールには、セキュリティで保護されたマウント ソリューション、セキュリティ ロック スロット (例: インカリスト ロック)、および I/O ポート アクセスのセキュリティ対策が必要です。不正なデバイスの接続を防止します。</span><span class="sxs-lookup"><span data-stu-id="9885a-117">Every certified compute module must have a secure mounting solution, a security lock slot (for example, Kensington lock), and I/O port access security measures to prevent the connection of unauthorized devices.</span></span> <span data-ttu-id="9885a-118">また、統合拡張ファームウェア インターフェイス ( EAP) 構成を使用して特定のポートを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9885a-118">You can also disable specific ports via Unified Extensible Firmware Interface (UEFI) configuration.</span></span>

<span data-ttu-id="9885a-119">認定済みのすべての計算モジュールは、既定で有効になっているトラステッド プラットフォーム モジュール (TP) 2.0 準拠テクノロジと一緒に出荷する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-119">Every certified compute module must ship with Trusted Platform Module (TPM) 2.0 compliant technology enabled by default.</span></span> <span data-ttu-id="9885a-120">TPM は、Teams Rooms リソース アカウントのログイン情報を暗号化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-120">TPM is used to encrypt the login information for the Teams Rooms resource account.</span></span>

<span data-ttu-id="9885a-121">セキュリティで保護されたブートは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9885a-121">Secure boot is enabled by default.</span></span> <span data-ttu-id="9885a-122">セキュア ブートは、元の機器製造元 (OEM) によって信頼されているソフトウェアのみを使用してデバイスを起動するために PC 業界のメンバーによって開発されたセキュリティ標準です。</span><span class="sxs-lookup"><span data-stu-id="9885a-122">Secure boot is a security standard developed by members of the PC industry to help make sure that a device boots using only software that is trusted by the Original Equipment Manufacturer (OEM).</span></span> <span data-ttu-id="9885a-123">PC が起動すると、ファームウェアは、(Option ROM とも呼ばれる)、EFI アプリケーション、オペレーティング システムなどのブート ソフトウェアの各部分の署名をチェックします。</span><span class="sxs-lookup"><span data-stu-id="9885a-123">When the PC starts, the firmware checks the signature of each piece of boot software, including UEFI firmware drivers (also known as Option ROMs), EFI applications, and the operating system.</span></span> <span data-ttu-id="9885a-124">署名が有効な場合は、PC が起動し、ファームウェアによってオペレーティング システムが制御されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-124">If the signatures are valid, the PC boots, and the firmware gives control to the operating system.</span></span> <span data-ttu-id="9885a-125">詳細については、「セキュア ブート」 [を参照してください](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。</span><span class="sxs-lookup"><span data-stu-id="9885a-125">For more information, see [Secure boot](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).</span></span>

<span data-ttu-id="9885a-126">KEYBOARD 設定へのアクセスは、物理キーボードとマウスを接続することでのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="9885a-126">Access to UEFI settings is only possible by attaching a physical keyboard and mouse.</span></span> <span data-ttu-id="9885a-127">これにより、Teams Rooms タッチ対応コンソールおよび Teams 会議室に接続されているその他のタッチ対応ディスプレイを介して それ以外の ED にアクセスすることを防止します。</span><span class="sxs-lookup"><span data-stu-id="9885a-127">This prevents being able to access UEFI via the Teams Rooms touch-enabled console as well as any other touch-enabled displays attached to Teams Rooms.</span></span>

<span data-ttu-id="9885a-128">カーネル ダイレクト メモリ アクセス (DMA) 保護は、Teams の会議室で有効になっている Windows 10 の設定です。</span><span class="sxs-lookup"><span data-stu-id="9885a-128">Kernel Direct Memory Access (DMA) Protection is a Windows 10 setting that is enabled on Teams Rooms.</span></span> <span data-ttu-id="9885a-129">この機能により、OS とシステムファームウェアは、DMA 対応のすべてのデバイスに対する悪意のある、意図しない DMA 攻撃からシステムを保護します。</span><span class="sxs-lookup"><span data-stu-id="9885a-129">With this feature, the OS and the system firmware protect the system against malicious and unintended DMA attacks for all DMA-capable devices:</span></span>

- <span data-ttu-id="9885a-130">起動プロセス中。</span><span class="sxs-lookup"><span data-stu-id="9885a-130">During the boot process.</span></span>

- <span data-ttu-id="9885a-131">OS 実行時に M.2 PCIe スロットや Thunderbolt 3 などの簡単にアクセス可能な内部/外部 DMA 対応ポートに接続されたデバイスによる悪意のある DMA に対して。</span><span class="sxs-lookup"><span data-stu-id="9885a-131">Against malicious DMA by devices connected to easily accessible internal/external DMA-capable ports, such as M.2 PCIe slots and Thunderbolt 3, during OS runtime.</span></span>

<span data-ttu-id="9885a-132">Teams の会議室では、HVC (分取り込み機能) によって保護されたコード整合性も有効になります。</span><span class="sxs-lookup"><span data-stu-id="9885a-132">Teams Rooms also enables Hypervisor-protected code integrity (HVCI).</span></span> <span data-ttu-id="9885a-133">HVCI によって提供される機能の 1 つは Credential Guard です。</span><span class="sxs-lookup"><span data-stu-id="9885a-133">One of the features provided by HVCI is Credential Guard.</span></span> <span data-ttu-id="9885a-134">Credential Guard には、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-134">Credential Guard provides the following benefits:</span></span>

- <span data-ttu-id="9885a-135">**ハードウェアのセキュリティ** NTLM、Kerberos、資格情報マネージャーは、Secure Boot や仮想化などのプラットフォームセキュリティ機能を利用して、資格情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="9885a-135">**Hardware security** NTLM, Kerberos, and Credential Manager take advantage of platform security features, including Secure Boot and virtualization, to protect credentials.</span></span>

- <span data-ttu-id="9885a-136">**仮想化ベースのセキュリティ** Windows NTLM と Kerberos の派生資格情報と他のシークレットは、実行中のオペレーティング システムから分離された保護された環境で実行されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-136">**Virtualization-based security** Windows NTLM and Kerberos derived credentials and other secrets run in a protected environment that is isolated from the running operating system.</span></span>

- <span data-ttu-id="9885a-137">**高度な永続的な脅威に対する保護を強化する** 資格情報マネージャーのドメイン資格情報、NTLM、Kerberos 派生資格情報が仮想化ベースのセキュリティを使用して保護されている場合、多くの対象指定攻撃で使用される資格情報の盗難攻撃の手法とツールはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9885a-137">**Better protection against advanced persistent threats** When Credential Manager domain credentials, NTLM, and Kerberos derived credentials are protected using virtualization-based security, the credential theft attack techniques and tools used in many targeted attacks are blocked.</span></span> <span data-ttu-id="9885a-138">管理者権限を持つオペレーティング システムで実行されているマルウェアは、仮想化ベースのセキュリティによって保護されている秘密を抽出できない。</span><span class="sxs-lookup"><span data-stu-id="9885a-138">Malware running in the operating system with administrative privileges can't extract secrets that are protected by virtualization-based security.</span></span>

## <a name="software-security"></a><span data-ttu-id="9885a-139">ソフトウェア セキュリティ</span><span class="sxs-lookup"><span data-stu-id="9885a-139">Software Security</span></span>

<span data-ttu-id="9885a-140">Microsoft Windows の起動後、Teams Rooms は Skype という名前のローカルの Windows ユーザー アカウントに自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9885a-140">After Microsoft Windows boots, Teams Rooms automatically signs into a local Windows user account named Skype.</span></span> <span data-ttu-id="9885a-141">Skype アカウントにはパスワードはありません。</span><span class="sxs-lookup"><span data-stu-id="9885a-141">The Skype account has no password.</span></span> <span data-ttu-id="9885a-142">Skype アカウント セッションをセキュリティで保護するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9885a-142">To make the Skype account session secure, the following steps are taken.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9885a-143">パスワードを変更したり、ローカルの Skype ユーザー アカウントを編集したりしない。</span><span class="sxs-lookup"><span data-stu-id="9885a-143">Don't change the password or edit the local Skype user account.</span></span> <span data-ttu-id="9885a-144">これにより、Teams の会議室が自動的にサインインしなからすのを防ぐ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-144">Doing so can prevent Teams Rooms from automatically signing in.</span></span>

<span data-ttu-id="9885a-145">Microsoft Teams Rooms アプリは、Windows 10 1903 以降の割り当て済みアクセス機能を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-145">The Microsoft Teams Rooms app runs using the Assigned Access feature found in Windows 10 1903 and later.</span></span> <span data-ttu-id="9885a-146">割り当てられた Access は、ユーザーに公開されるアプリケーション エントリ ポイントを制限する Windows 10 の機能です。</span><span class="sxs-lookup"><span data-stu-id="9885a-146">Assigned Access is a feature in Windows 10 that limits the application entry points exposed to the user.</span></span> <span data-ttu-id="9885a-147">これは、単一アプリ キオスク モードを有効にする機能です。</span><span class="sxs-lookup"><span data-stu-id="9885a-147">This is what enables single-app kiosk mode.</span></span> <span data-ttu-id="9885a-148">Shell 起動ツールを使用して、Teams Rooms はユーザー インターフェイスとして Windows デスクトップ アプリケーションを実行するキオスク デバイスとして構成されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-148">Using Shell Launcher, Teams Rooms is configured as a kiosk device that runs a Windows desktop application as the user interface.</span></span> <span data-ttu-id="9885a-149">Microsoft Teams Rooms アプリは、ユーザーがログオンするときに通常実行される既定のシェル (explorer.exe) を置き換える機能です。</span><span class="sxs-lookup"><span data-stu-id="9885a-149">The Microsoft Teams Rooms app replaces the default shell (explorer.exe) that usually runs when a user logs on.</span></span> <span data-ttu-id="9885a-150">つまり、従来のエクスプローラー シェルは起動されません。</span><span class="sxs-lookup"><span data-stu-id="9885a-150">In other words, the traditional Explorer shell does not get launched at all.</span></span> <span data-ttu-id="9885a-151">これにより、Windows 内の Microsoft Teams Rooms の脆弱性が大幅に軽減されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-151">This greatly reduces the Microsoft Teams Rooms vulnerability surface within Windows.</span></span> <span data-ttu-id="9885a-152">詳細については、「Windows デスクトップ エディション [でキオスクとデジタル署名を構成する」を参照してください](https://docs.microsoft.com/windows/configuration/kiosk-methods)。</span><span class="sxs-lookup"><span data-stu-id="9885a-152">For more information, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>

<span data-ttu-id="9885a-153">Teams Rooms でセキュリティ スキャンまたはインターネット セキュリティセンター (CIR) のベンチマークを実行する場合は、Skype ユーザー アカウントが Teams Rooms アプリ以外のアプリケーションの実行をサポートしなわないので、スキャンはローカル管理者アカウントのコンテキストでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="9885a-153">If you decide to run a security scan or a Center for Internet Security (CIS) benchmark on Teams Rooms, the scan can only run under the context of a local administrator account as the Skype user account doesn't support running applications other than the Teams Rooms app.</span></span> <span data-ttu-id="9885a-154">Skype ユーザー コンテキストに適用されるセキュリティ機能の多くは、他のローカル ユーザーには適用されません。そのため、これらのセキュリティ スキャンでは、Skype アカウントに適用される完全なセキュリティ ロックダウンは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9885a-154">Many of the security features applied to the Skype user context don't apply to other local users and, as a result, these security scans won't surface the full security lockdown applied to the Skype account.</span></span> <span data-ttu-id="9885a-155">そのため、Teams の会議室でローカル スキャンを実行する方法は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="9885a-155">Therefore, it is not recommended to run a local scan on Teams Rooms.</span></span> <span data-ttu-id="9885a-156">ただし、必要に応じて外部侵入テストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9885a-156">However, you can run external penetration tests if so desired.</span></span> <span data-ttu-id="9885a-157">この理由から、ローカル スキャンを実行する代わりに、Teams Rooms デバイスに対して外部侵入テストを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9885a-157">Because of this, we recommend that you run external penetration tests against Teams Rooms devices instead of running local scans.</span></span>

<span data-ttu-id="9885a-158">さらに、非管理機能の使用を制限するために、ポリシーのロックダウンが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-158">Additionally, lock down policies are applied to limit non-administrative features from being used.</span></span> <span data-ttu-id="9885a-159">割り当て済み Access ポリシーの対象ではない、安全でない可能性があるキーボードの組み合わせを傍受およびブロックするには、キーボード フィルターが有効になります。</span><span class="sxs-lookup"><span data-stu-id="9885a-159">A keyboard filter is enabled to intercept and block potentially insecure keyboard combinations that aren't covered by Assigned Access policies.</span></span> <span data-ttu-id="9885a-160">ローカルまたはドメインの管理者権限を持つユーザーだけが、Teams ルームを管理するために Windows にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="9885a-160">Only users with local or domain administrative rights are permitted to sign into Windows to manage Teams Rooms.</span></span> <span data-ttu-id="9885a-161">Microsoft Teams Rooms デバイス上の Windows に適用されるこれらのポリシーおよび他のポリシーは、製品ライフサイクルの間、継続的に評価およびテストされます。</span><span class="sxs-lookup"><span data-stu-id="9885a-161">These and other policies applied to Windows on Microsoft Teams Rooms devices are continually assessed and tested during the product lifecycle.</span></span>

## <a name="account-security"></a><span data-ttu-id="9885a-162">アカウントのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="9885a-162">Account Security</span></span>

<span data-ttu-id="9885a-163">Teams 会議室デバイスには、"管理者" という名前の管理アカウントと既定のパスワードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9885a-163">Teams Rooms devices include an administrative account named "Admin" with a default password.</span></span> <span data-ttu-id="9885a-164">セットアップが完了したら、できるだけ早く既定のパスワードを変更することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="9885a-164">We strongly recommend that you change the default password as soon as possible after you complete setup.</span></span>

<span data-ttu-id="9885a-165">Teams Rooms デバイスを適切に操作するために管理者アカウントは必要ありません。名前を変更したり、削除したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9885a-165">The Admin account isn't required for proper operation of Teams Rooms devices and can be renamed or even deleted.</span></span> <span data-ttu-id="9885a-166">ただし、管理者アカウントを削除する前に、Teams Rooms デバイスに組み込みのアカウントを削除する前に、別のローカル管理者アカウントを設定してください。</span><span class="sxs-lookup"><span data-stu-id="9885a-166">However, before you delete the Admin account, make sure that you set up an alternate local administrator account configured before removing the one that ships with Teams Rooms devices.</span></span> <span data-ttu-id="9885a-167">組み込みの Windows ツールまたは PowerShell を使用してローカルの Windows アカウントのパスワードを変更する方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9885a-167">For more information on how to change a password for a local Windows account using built-in Windows tools or PowerShell, see the following:</span></span>

- [<span data-ttu-id="9885a-168">Windows パスワードを変更またはリセットする</span><span class="sxs-lookup"><span data-stu-id="9885a-168">Change or reset your Windows password</span></span>](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [<span data-ttu-id="9885a-169">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="9885a-169">Set-LocalUser</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

<span data-ttu-id="9885a-170">ローカルの Windows 管理者グループにドメイン アカウントをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9885a-170">You can also import domain accounts into the local Windows Administrator group.</span></span> <span data-ttu-id="9885a-171">Intune を使用して、Azure ADアカウントに対してこれを行います。</span><span class="sxs-lookup"><span data-stu-id="9885a-171">You can do this for Azure AD accounts by using Intune.</span></span> <span data-ttu-id="9885a-172">詳細については、「Policy [CSP – RestrictedGroups」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)。</span><span class="sxs-lookup"><span data-stu-id="9885a-172">For more information, see [Policy CSP – RestrictedGroups.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups).</span></span>

> [!CAUTION]
> <span data-ttu-id="9885a-173">別のローカル またはドメイン アカウントにローカル管理者権限を付与する前に管理者アカウントを削除または無効にすると、Teams Rooms デバイスを管理する機能が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-173">If you delete or disable the Admin account before granting local Administrator permissions to another local or domain account, you may lose the ability to administer the Teams Rooms device.</span></span> <span data-ttu-id="9885a-174">この場合は、デバイスを元の設定にリセットし、セットアップ プロセスを再度完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-174">If this happens, you'll need to reset the device back to its original settings and complete the setup process again.</span></span>
>
> <span data-ttu-id="9885a-175">Skype ユーザー アカウントにローカルの管理者権限を付与しない。</span><span class="sxs-lookup"><span data-stu-id="9885a-175">Don't grant local Administrator permissions to the Skype user account.</span></span>

<span data-ttu-id="9885a-176">Windows 構成デザイナーを使用して、Windows 10 プロビジョニング パッケージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9885a-176">Windows Configuration Designer can be used to create Windows 10 provisioning packages.</span></span> <span data-ttu-id="9885a-177">ローカルの管理者パスワードの変更と共に、コンピューター名の変更や Azure Active Directory への登録なども行います。</span><span class="sxs-lookup"><span data-stu-id="9885a-177">Along with changing the local Admin password, you can also do things like changing the machine name and enrolling into Azure Active Directory.</span></span> <span data-ttu-id="9885a-178">Windows 構成デザイナープロビジョニング パッケージの作成の詳細については [、「Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)のプロビジョニング パッケージ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9885a-178">For more information on creating a Windows Configuration Designer provisioning package, see [Provisioning packages for Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="9885a-179">Teams にサインインするには、Teams 会議室デバイスごとにリソース アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-179">You need to create a resource account for each Teams Rooms device so that it can sign into Teams.</span></span> <span data-ttu-id="9885a-180">このアカウントでは、2 要素認証または多要素認証を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9885a-180">You can't use two-factor or multi-factor authentication with this account.</span></span> <span data-ttu-id="9885a-181">2 つ目の要因を必要とすると、再起動後にアカウントが Teams Rooms アプリに自動的にサインインできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-181">Requiring a second factor would prevent the account from being able to automatically sign into the Teams Rooms app after a reboot.</span></span> <span data-ttu-id="9885a-182">ただし、このアカウントのセキュリティを強化するには、最新の認証を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="9885a-182">However, you can enable Modern Authentication for additional security for this account.</span></span> <span data-ttu-id="9885a-183">さらに、リソース アカウントに対して場所に基づく条件付きアクセス ポリシーを展開して、割り当てされていない場所からアカウントにサインインするのを防ぐ方法もあります。</span><span class="sxs-lookup"><span data-stu-id="9885a-183">In addition, location based Conditional Access policies can be deployed for the resource account to prevent signing into the account from an unapproved location.</span></span> <span data-ttu-id="9885a-184">詳細については、「条件付き [アクセス ポリシーでの場所の条件の使用」を参照してください。](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)</span><span class="sxs-lookup"><span data-stu-id="9885a-184">For more information, see [Using the location condition in a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)</span></span>

<span data-ttu-id="9885a-185">可能であれば、Azure AD作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9885a-185">We recommend that you create the resource account in Azure AD, if possible.</span></span> <span data-ttu-id="9885a-186">同期されたアカウントは、ハイブリッド展開で Teams Rooms と動作しますが、これらの同期されたアカウントは、多くの場合、Teams の会議室へのサインインに問題を持ち、トラブルシューティングが難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-186">While a synced account can work with Teams Rooms in hybrid deployments, these synced accounts often have difficulty signing into Teams Rooms and can be difficult to troubleshoot.</span></span> <span data-ttu-id="9885a-187">サードパーティ フェデレーション サービスを使用してリソース アカウントの資格情報を認証する場合は、サード パーティ IDP が属性を設定して応答します `wsTrustResponse` `urn:oasis:names:tc:SAML:1.0:assertion` 。</span><span class="sxs-lookup"><span data-stu-id="9885a-187">If you choose to use a third-party federation service to authenticate the credentials for the resource account, ensure the third-party IDP responds with the `wsTrustResponse` attribute set to `urn:oasis:names:tc:SAML:1.0:assertion`.</span></span>

## <a name="network-security"></a><span data-ttu-id="9885a-188">ネットワーク セキュリティ</span><span class="sxs-lookup"><span data-stu-id="9885a-188">Network Security</span></span>

<span data-ttu-id="9885a-189">一般に、Teams Rooms には、Microsoft Teams クライアントと同じネットワーク要件があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-189">Generally, Teams Rooms has the same network requirements as any Microsoft Teams client.</span></span> <span data-ttu-id="9885a-190">ファイアウォールや他のセキュリティ デバイスを介したアクセスは、Teams 会議室の場合、他の Microsoft Teams クライアントの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9885a-190">Access through firewalls and other security devices is the same for Teams Rooms as for any other Microsoft Teams client.</span></span> <span data-ttu-id="9885a-191">Teams ルームに固有の、Teams の "必須" として表示されるカテゴリは、ファイアウォールで開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-191">Specific to Teams Rooms, the categories listed as "required" for Teams must be open on your firewall.</span></span> <span data-ttu-id="9885a-192">Teams 会議室には、Windows Update、Microsoft Store、Microsoft Intune (デバイスの管理に Microsoft Intune を使用している場合) へのアクセスも必要です。</span><span class="sxs-lookup"><span data-stu-id="9885a-192">Teams Rooms also needs access to Windows Update, Microsoft Store, and Microsoft Intune (if you use Microsoft Intune to manage your devices).</span></span> <span data-ttu-id="9885a-193">Microsoft Teams の会議室に必要な IP と URL の完全な一覧については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9885a-193">For the full list of IPs and URLs required for Microsoft Teams Rooms, see:</span></span>

- <span data-ttu-id="9885a-194">**Microsoft Teams Office** [365 の URL と IP アドレス範囲を使用する](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="9885a-194">**Microsoft Teams** [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)</span></span>
- <span data-ttu-id="9885a-195">**Windows Update で** [WSUS を構成する](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)</span><span class="sxs-lookup"><span data-stu-id="9885a-195">**Windows Update** [Configure WSUS](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)</span></span>
- <span data-ttu-id="9885a-196">**ビジネスおよび**[教育向け Microsoft Store の Microsoft Store の前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)</span><span class="sxs-lookup"><span data-stu-id="9885a-196">**Microsoft Store** [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)</span></span>
- <span data-ttu-id="9885a-197">**Microsoft Intune** [Network Enpoints for Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)</span><span class="sxs-lookup"><span data-stu-id="9885a-197">**Microsoft Intune** [Network Enpoints for Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)</span></span>

<span data-ttu-id="9885a-198">Microsoft Teams Rooms Premium の Microsoft Teams Rooms 管理サービス コンポーネントを使用している場合は、Teams 会議室が次の URL にアクセスできる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="9885a-198">If you're using the Microsoft Teams Rooms managed services component of Microsoft Teams Rooms Premium, you also need to make sure that Teams Rooms can access the following URLs:</span></span>

- <span data-ttu-id="9885a-199">global.azure-devices-provisioning.net</span><span class="sxs-lookup"><span data-stu-id="9885a-199">global.azure-devices-provisioning.net</span></span>
- <span data-ttu-id="9885a-200">gj3ftstorage.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="9885a-200">gj3ftstorage.blob.core.windows.net</span></span>
- <span data-ttu-id="9885a-201">gj3ft-hub.azure-devices.net</span><span class="sxs-lookup"><span data-stu-id="9885a-201">gj3ft-hub.azure-devices.net</span></span>
- <span data-ttu-id="9885a-202">iothubsgagwt5wgvwg6.azure-devices.net</span><span class="sxs-lookup"><span data-stu-id="9885a-202">iothubsgagwt5wgvwg6.azure-devices.net</span></span>
- <span data-ttu-id="9885a-203">blobssgagwt5wgvwg6.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="9885a-203">blobssgagwt5wgvwg6.blob.core.windows.net</span></span>
- <span data-ttu-id="9885a-204">prod-48.westus.logic.azure.com</span><span class="sxs-lookup"><span data-stu-id="9885a-204">prod-48.westus.logic.azure.com</span></span>
- <span data-ttu-id="9885a-205">prod-08.westus.logic.azure.com</span><span class="sxs-lookup"><span data-stu-id="9885a-205">prod-08.westus.logic.azure.com</span></span>
- <span data-ttu-id="9885a-206">prod-62.westus.logic.azure.com</span><span class="sxs-lookup"><span data-stu-id="9885a-206">prod-62.westus.logic.azure.com</span></span>
- <span data-ttu-id="9885a-207">prod-65.westus.logic.azure.com</span><span class="sxs-lookup"><span data-stu-id="9885a-207">prod-65.westus.logic.azure.com</span></span>
- <span data-ttu-id="9885a-208">prod-05.westus.logic.azure.com</span><span class="sxs-lookup"><span data-stu-id="9885a-208">prod-05.westus.logic.azure.com</span></span>

<span data-ttu-id="9885a-209">Teams Rooms は、セキュリティ更新プログラムを含む最新の Windows 更新プログラムに自動的にパッチを適用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="9885a-209">Teams Rooms is configured to automatically keep itself patched with the latest Windows updates, including security updates.</span></span> <span data-ttu-id="9885a-210">Teams Rooms は、事前に設定されたローカル ポリシーを使用して、毎日午前 2 時から保留中の更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9885a-210">Teams Rooms installs any pending updates every day beginning at 2:00am using a pre-set local policy.</span></span> <span data-ttu-id="9885a-211">追加のツールを使用して Windows 更新プログラムを展開および適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9885a-211">There is no need to use additional tools to deploy and apply Windows Updates.</span></span> <span data-ttu-id="9885a-212">追加のツールを使用して更新プログラムを展開および適用すると、Windows パッチのインストールが遅れて、展開の安全性が低い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-212">Using additional tools to deploy and apply updates can delay the installation of Windows patches and thus lead to a less secure deployment.</span></span> <span data-ttu-id="9885a-213">Teams Rooms アプリは、Microsoft Store を使用して展開されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-213">The Teams Rooms app is deployed using the Microsoft Store.</span></span> <span data-ttu-id="9885a-214">デバイスに Microsoft Teams Rooms Standard のライセンスが適用されている場合、夜間のパッチ適用プロセス中に、すべての新しいバージョンのアプリが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9885a-214">If your devices are licensed with Microsoft Teams Rooms Standard, any new versions of the app are automatically installed during the nightly patching process.</span></span> <span data-ttu-id="9885a-215">デバイスに Microsoft Teams Rooms Premium のライセンスが与え、Microsoft Managed Service に登録されている場合、新しいバージョンの Teams Rooms アプリは、定義されたロールアウトプランごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9885a-215">If your devices are licensed with Microsoft Teams Rooms Premium and enrolled in the Microsoft Managed Service, new versions of the Teams Rooms app are installed per your defined rollout plan.</span></span>

<span data-ttu-id="9885a-216">Teams Rooms デバイスは、ほとんどの 802.1X または他のネットワーク ベースのセキュリティ プロトコルで動作します。</span><span class="sxs-lookup"><span data-stu-id="9885a-216">Teams Rooms devices work with most 802.1X or other network-based security protocols.</span></span> <span data-ttu-id="9885a-217">ただし、可能性があるすべてのネットワーク セキュリティ構成に対して Teams Rooms をテストできるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="9885a-217">However, we're not able to test Teams Rooms against all possible network security configurations.</span></span> <span data-ttu-id="9885a-218">そのため、ネットワーク パフォーマンスの問題をトレースできるパフォーマンスの問題が発生した場合は、組織でこれらのプロトコルが構成されている場合は無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-218">Therefore, if performance issues arise that can be traced to network performance issues, you may need to disable these protocols if they're configured in your organization.</span></span>

<span data-ttu-id="9885a-219">リアルタイム メディアの最適なパフォーマンスを得る場合は、プロキシ サーバーや他のネットワーク セキュリティ デバイスをバイパスする Teams メディア トラフィックを構成することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="9885a-219">For optimum performance of real time media, we strongly recommend that you configure Teams media traffic to bypass proxy servers and other network security devices.</span></span> <span data-ttu-id="9885a-220">リアルタイム メディアは待機時間が非常に高く、プロキシ サーバーとネットワーク セキュリティ デバイスは、ユーザーのビデオと音声の品質を大幅に低下させる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-220">Real time media is very latency sensitive and proxy servers and network security devices can significantly degrade users' video and audio quality.</span></span> <span data-ttu-id="9885a-221">また、Teams メディアは既に暗号化されていますので、プロキシ サーバーを経由してトラフィックを通過するメリットはありません。</span><span class="sxs-lookup"><span data-stu-id="9885a-221">Also, because Teams media is already encrypted, there's no tangible benefit from passing the traffic through a proxy server.</span></span> <span data-ttu-id="9885a-222">詳細については [、「Networking up (クラウドへ)](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) — Microsoft Teams および Microsoft Teams Rooms を使用してメディアのパフォーマンスを向上させるネットワーク推奨事項について説明する 1 人の設計者の力である」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9885a-222">For more information, see [Networking up (to the cloud) — One architect’s viewpoint](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) which discusses network recommendations to improve the performance of media with Microsoft Teams and Microsoft Teams Rooms.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9885a-223">Teams 会議室は、認証されたプロキシ サーバーをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="9885a-223">Teams Rooms doesn't support authenticated proxy servers.</span></span>

<span data-ttu-id="9885a-224">Teams Rooms デバイスは内部 LAN に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9885a-224">Teams Rooms devices don't need to connect to an internal LAN.</span></span> <span data-ttu-id="9885a-225">直接インターネットにアクセスできるセキュリティで保護されたネットワーク セグメントに Teams Rooms を配置します。</span><span class="sxs-lookup"><span data-stu-id="9885a-225">Consider placing Teams Rooms in a secure network segment with direct Internet access.</span></span> <span data-ttu-id="9885a-226">内部 LAN が侵害された場合、Teams Rooms に対する攻撃ベクターの機会は削減されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-226">If your internal LAN becomes compromised, the attack vector opportunities towards Teams Rooms will be reduced.</span></span>

<span data-ttu-id="9885a-227">Teams Rooms デバイスを有線ネットワークに接続することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="9885a-227">We strongly recommend that you connect your Teams Rooms devices to a wired network.</span></span> <span data-ttu-id="9885a-228">Teams Rooms デバイスでのワイヤレス ネットワークの使用は推奨または認定されていません。</span><span class="sxs-lookup"><span data-stu-id="9885a-228">The use of wireless networks on Teams Rooms devices isn't recommended or certified.</span></span> <span data-ttu-id="9885a-229">Wi-Fi Sense などの一部の接続機能は、既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9885a-229">Some connectivity features, such as Wi-Fi Sense, are disabled by default.</span></span>

<span data-ttu-id="9885a-230">近接参加と他の Teams 会議室の機能は、Bluetooth。</span><span class="sxs-lookup"><span data-stu-id="9885a-230">Proximity Join and other Teams Rooms features rely on Bluetooth.</span></span> <span data-ttu-id="9885a-231">ただし、Teams Rooms Bluetooth実装を行う場合、Teams Rooms デバイスへの外部デバイス接続は許可されません。</span><span class="sxs-lookup"><span data-stu-id="9885a-231">However, the Bluetooth implementation on Teams Rooms devices doesn't allow for an external device connection to a Teams Rooms device.</span></span> <span data-ttu-id="9885a-232">Bluetooth Teams Rooms デバイスでのテクノロジの使用は、現在、広告ビーコンと近位接続の要求に制限されています。</span><span class="sxs-lookup"><span data-stu-id="9885a-232">Bluetooth technology use on Teams Rooms devices is currently limited to advertising beacons and prompted proximal connections.</span></span> <span data-ttu-id="9885a-233">プロトコル `ADV_NONCONN_INT` データユニット (PDU) の種類は、広告ビーコンで使用されます。</span><span class="sxs-lookup"><span data-stu-id="9885a-233">The `ADV_NONCONN_INT` protocol data unit (PDU) type is used in the advertising beacon.</span></span> <span data-ttu-id="9885a-234">この PDU の種類は、聞き取りデバイスに情報を提供する接続不可のデバイス用です。</span><span class="sxs-lookup"><span data-stu-id="9885a-234">This PDU type is for non-connectable devices advertising information to the listening device.</span></span> <span data-ttu-id="9885a-235">これらの機能Bluetoothデバイスのペアリングに問題はありません。</span><span class="sxs-lookup"><span data-stu-id="9885a-235">There is no Bluetooth device pairing as part of these features.</span></span> <span data-ttu-id="9885a-236">このプロトコルのBluetoothは、SIG Web サイトBluetooth [参照してください](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。</span><span class="sxs-lookup"><span data-stu-id="9885a-236">Additional details on Bluetooth protocols can be found on the [Bluetooth SIG website](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).</span></span>