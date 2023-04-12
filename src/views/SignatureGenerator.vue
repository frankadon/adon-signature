<template>
  <div class="row">
    <div class="col-sm-4">
      <div class="my-card">
        <form class="form">
          <h4>Signature form</h4>
          <div class="radio-group">
            <h5>Options</h5>
            <div class="form-check">
              <input
                @click="$event => showAOGSignature()"
                type="radio"
                name="sig"
                class="form-check-input"
                id="aogsignature"
                checked
              >
              <label class="form-check-label" for="aogsignature">
                AOG Signature
              </label>
            </div>
            <div v-if="isAOGSig" class="my-card">
              <div class="form-check">
                <input
                  @click="getOption1()"
                  class="form-check-input"
                  name="options"
                  type="radio"
                  value="option1"
                  id="option1"
                  checked
                />
                <label class="form-check-label" for="option1">
                  Phone only
                </label>
              </div>
              <div class="form-check">
                <input
                  @click="getOption2()"
                  class="form-check-input"
                  name="options"
                  type="radio"
                  value="option2"
                  id="option2"
                />
                <label class="form-check-label" for="option2">
                  Mobile only
                </label>
              </div>
              <div class="form-check">
                <input
                  @click="getOption3()"
                  class="form-check-input"
                  name="options"
                  type="radio"
                  value="option3"
                  id="option3"
                />
                <label class="form-check-label" for="option3">
                  Both number
                </label>
              </div>
            </div>
            <div class="form-check">
              <input
                @click="$event => showAOWSignature()"
                type="radio"
                name="sig"
                class="form-check-input"
                id="aowsignature"
              >
              <label class="form-check-label" for="aowsignature">
                AOW Signature
              </label>
            </div>
            <div v-if="isAOWSig" class="my-card">
            <div class="form-check">
              <input
                @click="getOption1()"
                class="form-check-input"
                name="options"
                type="radio"
                value="option1"
                id="option1"
                checked
              />
              <label class="form-check-label" for="option1">
                Phone only
              </label>
            </div>
            <div class="form-check">
              <input
                @click="getOption2()"
                class="form-check-input"
                name="options"
                type="radio"
                value="option2"
                id="option2"
              />
              <label class="form-check-label" for="option2">
                Mobile only
              </label>
            </div>
            <div class="form-check">
              <input
                @click="getOption3()"
                class="form-check-input"
                name="options"
                type="radio"
                value="option3"
                id="option3"
              />
              <label class="form-check-label" for="option3">
                Both number
              </label>
            </div>
          </div>
          </div>

          <div v-if="isAOGSig">
            <div class="form-floating mb-2 mt-2">
              <input
                v-model="sigName"
                class="form-control"
                name="name"
                type="text"
                id="signame"
                :placeholder="sigName"
              />
              <label for="signame">Name</label>
            </div>
            <div class="form-floating mb-2">
              <input
                v-model="sigPosition"
                class="form-control"
                name="position"
                type="text"
                id="sigposition"
                :placeholder="sigPosition"
              />
              <label for="sigposition">Position</label>
            </div>
            <div class="form-floating mb-2">
              <input
                v-if="isShowPhone"
                v-model="sigPhone"
                class="form-control"
                name="phone"
                type="text"
                id="sigphone"
                placeholder="Phone"
              />
              <label v-if="isShowPhone" for="sigphone">Phone</label>
            </div>
            <div class="form-floating mb-2">
              <input
                v-if="isShowMobile"
                v-model="sigMobile"
                class="form-control"
                id="mobile-number"
                name="mobile"
                type="text"
                :placeholder="sigMobile"
              />
              <label v-if="isShowMobile" for="mobile-number">Mobile</label>
            </div>
          </div>

          <div v-if="isAOWSig">
            <div class="form-floating mb-2 mt-2">
              <input
                v-model="sigName"
                class="form-control"
                name="name"
                type="text"
                id="signame"
                :placeholder="sigName"
              />
              <label for="signame">Name</label>
            </div>
            <div class="form-floating mb-2">
              <input
                v-model="sigPosition"
                class="form-control"
                name="position"
                type="text"
                id="sigposition"
                :placeholder="sigPosition"
              />
              <label for="sigposition">Position</label>
            </div>
            <div class="form-floating mb-2 mt-2">
              <input
                v-model="sigEmail"
                class="form-control"
                name="email"
                type="email"
                id="email"
                :placeholder="sigEmail"
              />
              <label for="sigemail">Email</label>
            </div>
            <div class="form-floating mb-2">
              <input
                v-if="isShowPhone"
                v-model="sigPhone"
                class="form-control"
                name="phone"
                type="text"
                id="sigphone"
                placeholder="Phone"
              />
              <label v-if="isShowPhone" for="sigphone">Phone</label>
            </div>
            <div class="form-floating mb-2">
              <input
                v-if="isShowMobile"
                v-model="sigMobile"
                class="form-control"
                id="mobile-number"
                name="mobile"
                type="text"
                :placeholder="sigMobile"
              />
              <label v-if="isShowMobile" for="mobile-number">Mobile</label>
            </div>
          </div>
          

          <div class="action-btn">
            <Button
              v-if="isAOGSig"
              @click="generateEmailSignature()"
              Text="Generate"
              bgColor="primary"
            />
            <Button
              v-if="isAOWSig"
              @click="generateParadiseSignature()"
              Text="Generate"
              bgColor="primary"
            />
          </div>
        </form>
      </div>
    </div>
    <div class="col-sm-8">
      <div class="my-card">
          <h4>Preview</h4>
          <div v-if="isAOGSig" class="signature-data">
            <div class="data">
              <!-- <div class="logo-aog">
                <img src="../assets/AOG-logo.png" alt="logo" />
              </div> -->
              <SignatureLogo
                clsname="logo-aog"
                logolink="https://adongroup.com.au/wp-content/uploads/2022/11/AOG-logo.png"
              />
              <div class="info">
                <SignatureName :text="sigName" />
                <SignaturePosition :text="sigPosition"/>
                <p class="links">
                  <SignatureLink 
                    v-if="isShowPhone"
                    link="https://adongroup.com.au/wp-content/uploads/2022/11/icon-01.png"
                    :text="sigPhone"
                    href="tel:07 5586 1400"
                  />
                  <br v-if="isShowPhone" />
                  <SignatureLink
                    v-if="isShowMobile"
                    link="https://adongroup.com.au/wp-content/uploads/2022/11/icon-mobile-01.png"
                    :text="sigMobile"
                    href="tel: 0401 736 730"
                  />
                  <br v-if="isShowMobile" />
                  <SignatureLink
                    link="https://adongroup.com.au/wp-content/uploads/2022/11/icon-02.png"
                    text="www.adongroup.com.au"
                    href="http://www.adongroup.com.au"
                  />
                </p>
              </div>
              <div class="partner">
                <img src="../assets/google-partner.png" alt="partners" />
              </div>
            </div>
            <div class="disclaimer">
              <Disclaimer text="This email, its contents and any attachments are strictly
                confidential. They must not be used, distributed, copied or read
                by any person other than the addressee. Unauthorised use,
                disclosure, copying or reliance on the contents of and
                attachments to this email by anyone other than the addressee may
                be unlawful. If you have received this email and attachments in
                error please contact us at Ad on Group immediately to facilitate
                its return."/>
            </div>
          </div>
          <div v-if="isAOWSig" class="signature-data-paradise">
            <div class="data">
              <SignatureLogo
                clsname="logo-aow"
                logolink="https://adonworkforce.com.au/wp-content/uploads/2023/03/Ad-on-Workforce-logo.png"
                text="A Division of Ad On Group"
              />
              <div class="info">
                <SignatureName :text="sigName" />
                <SignaturePosition :text="sigPosition"/>
                <p class="links">
                  <SignatureLink
                    v-if="isShowPhone"
                    link="https://adongroup.com.au/wp-content/uploads/2022/11/icon-01.png"
                    :text="sigPhone"
                    href="tel:07 5586 1400"
                  />
                  <br v-if="isShowPhone" />
                  <SignatureLink
                    v-if="isShowMobile"
                    link="https://adongroup.com.au/wp-content/uploads/2022/11/icon-mobile-01.png"
                    :text="sigMobile"
                    href="tel: 0401 736 730"
                  />
                  <br v-if="isShowMobile" />
                  <SignatureLink
                    link="https://adongroup.com.au/wp-content/uploads/2022/11/icon-02.png"
                    :text="sigEmail"
                    :href="'mailto'+':'+sigEmail"
                  />
                  <br>
                  <SignatureLink
                    link="https://adongroup.com.au/wp-content/uploads/2022/11/icon-02.png"
                    text="www.adonworkforce.com.au"
                    href="http://www.adonworkforce.com.au"
                  />
                </p>
              </div>
              <div class="partner">
                <SignatureLogo
                  clsname="logo-aogaow"
                  logolink="https://adongroup.com.au/wp-content/uploads/2022/11/AOG-logo.png"
                />
              </div>
            </div>
            <div class="disclaimer">
              <Disclaimer text="This email, its contents and any attachments are strictly
                confidential. They must not be used, distributed, copied or read
                by any person other than the addressee. Unauthorised use,
                disclosure, copying or reliance on the contents of and
                attachments to this email by anyone other than the addressee may
                be unlawful. If you have received this email and attachments in
                error please contact us at Ad on Group immediately to facilitate
                its return."/>
            </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
// icons
import PhoneIcon from "../assets/icons/icon-01.png"
import MobileIcon from "../assets/icons/icon-mobile-01.png"
import GlobeIcon from "../assets/icons/icon-02.png"
import AOWLogo from "../assets/Ad-on-Workforce-logo.png"
import AOGLogo from "../assets/AOG-logo.png"


import Button from "@/components/Button.vue";
import SignatureName from "@/components/signature/SignatureName.vue";
import SignaturePosition from "@/components/signature/SignaturePosition.vue";
import Disclaimer from "@/components/signature/Disclaimer.vue";
import SignatureLink from "@/components/signature/SignatureLink.vue";
import SignatureLogo from "@/components/SignatureLogo.vue";

export default {
  name: "Home",
  data() {
    return {
      sigName: "Name",
      sigPosition: "Position",
      sigPhone: "07 5586 1400",
      sigMobile: "0401 736 730",
      sigEmail: "info@adonworkforce.com.au",
      isShowPhone: true,
      isShowMobile: false,
      isAOGSig: true,
      isAOWSig: false,
      phoneIcon: PhoneIcon,
      mobileIcon: MobileIcon,
      globeIcon: GlobeIcon,
      aowLogo: AOWLogo,
      aogLogo: AOGLogo,
    };
  },
  components: {
    Button,
    SignatureName,
    SignaturePosition,
    Disclaimer,
    SignatureLink,
    SignatureLogo
  },
  mounted() {
    // const options = document.querySelector(
    //   ".radio-group input[name='options']"
    // );
    // console.log(options.value);
    // if (options.value === "option1") {
    //   console.log(this.option2);
    // }
  },
  methods: {
    showAOGSignature() {
      this.isAOGSig = true;
      this.isAOWSig = false;
    },
    showAOWSignature() {
      this.isAOGSig = false;
      this.isAOWSig = true;
    },
    getOption1() {
      this.isShowPhone = true;
      this.isShowMobile = false;
    },
    getOption2() {
      this.isShowPhone = false;
      this.isShowMobile = true;
    },
    getOption3() {
      this.isShowPhone = true;
      this.isShowMobile = true;
    },
    generateEmailSignature() {
      const name = this.sigName;
      const position = this.sigPosition;
      const phone = this.sigPhone;
      const mobile = this.sigMobile;
      // const email = this.sigEmail;
      const logoPartnerb64 =
        "https://adongroup.com.au/wp-content/uploads/2022/11/google-partner.png";
      if (this.isShowPhone == true && this.isShowMobile == false) {
        const openSig = document.open("", "", "fullscreen=yes");
        openSig.document.write(
          "<!DOCTYPE html PUBLIC '-//W3C//DTD XHTML 1.0 Transitional//EN' 'http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd'><html xmlns='http://www.w3.org/1999/xhtml'> <head> <meta http-equiv='Content-Type' content='text/html; charset=utf-8'/> <title>Ad On Group - Digital Marketing Specialists</title> </head> <body> <table width='650' height='170' border='0' cellspacing='0' cellpadding='0' style=' border-collapse: collapse; background: url(https://adongroup.com.au/wp-content/uploads/2022/11/bg-gradiant.png); background-repeat: no-repeat; background-size: cover; border-radius: 15px; color: white; font-family: sans-serif; line-height: 0px; font-size: 1px; padding: 0px; border-spacing: 0px; margin: 0; text-decoration: none; '> <tr> <td width='180'><img style='width: 180px; height: auto;' src='https://adongroup.com.au/wp-content/uploads/2022/11/AOG-logo.png' alt=''/></td><td> <table width='95%' height='85%' border='0' cellspacing='0' cellpadding='0' style='margin-left: 10px; margin-top: 20px;'> <tr> <td height='15' style='font-size: 15px; color: white;'><b>" +
            name +
            "</b></td></tr><tr> <td height='11' style='font-size: 11px; line-height: 1; color: white;'><b>" +
            position +
            " </b></td></tr><tr> <td height='50' style='line-height: 1.2; font-size: 10px;'> <p> <a style='text-decoration: none; color: white;' href='tel:" +
            phone +
            "'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-01.png' alt='phone'/> <span style='font-size: 12px;'>&nbsp " +
            phone +
            "</span> </a> <br/> <a style='text-decoration: none; color: white;' href='https://www.adongroup.com.au'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-02.png' alt='internet'/> <span style='font-size: 12px;'>&nbsp www.adongroup.com.au</span> </a> </p></td></tr></table> </td><td width='250px'><img style='width: 250px; height: auto; float: right;' src='" +
            logoPartnerb64 +
            "' alt='Partner'/></td></tr><tr> <td colspan='3' height='40' style='line-height: 1.2; font-size: 8px;'> <p style='font-size: 8px; margin-left: 12px; margin-right: 12px; margin-bottom: 10px;'> This email, its contents and any attachments are strictly confidential. They must not be used, distributed, copied or read by any person other than the addressee. Unauthorised use, disclosure, copying or reliance on the contents of and attachments to this email by anyone other than the addressee may be unlawful. If you have received this email and attachments in error please contact us at Ad on Group immediately to facilitate its return. </p></td></tr></table> </body></html>"
        );
        openSig.document.close();
      } else if (this.isShowMobile == true && this.isShowPhone == false) {
        const openSig = document.open("", "", "fullscreen=yes");
        openSig.document.write(
          "<!DOCTYPE html PUBLIC '-//W3C//DTD XHTML 1.0 Transitional//EN' 'http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd'><html xmlns='http://www.w3.org/1999/xhtml'> <head> <meta http-equiv='Content-Type' content='text/html; charset=utf-8'/> <title>Ad On Group - Digital Marketing Specialists</title> </head> <body> <table width='650' height='170' border='0' cellspacing='0' cellpadding='0' style=' border-collapse: collapse; background: url(https://adongroup.com.au/wp-content/uploads/2022/11/bg-gradiant.png); background-repeat: no-repeat; background-size: cover; border-radius: 15px; color: white; font-family: sans-serif; line-height: 0px; font-size: 1px; padding: 0px; border-spacing: 0px; margin: 0; text-decoration: none; '> <tr> <td width='180'><img style='width: 180px; height: auto;' src='https://adongroup.com.au/wp-content/uploads/2022/11/AOG-logo.png' alt=''/></td><td> <table width='95%' height='85%' border='0' cellspacing='0' cellpadding='0' style='margin-left: 10px; margin-top: 20px;'> <tr> <td height='15' style='font-size: 15px; color: white;'><b>" +
            name +
            "</b></td></tr><tr> <td height='11' style='font-size: 11px; line-height: 1; color: white;'><b>" +
            position +
            " </b></td></tr><tr> <td height='50' style='line-height: 1.2; font-size: 10px;'> <p> <a style='text-decoration: none; color: white;' href='tel:" +
            mobile +
            "'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-mobile-01.png' alt='phone'/> <span style='font-size: 12px;'>&nbsp " +
            mobile +
            "</span> </a> <br/> <a style='text-decoration: none; color: white;' href='https://www.adongroup.com.au'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-02.png' alt='internet'/> <span style='font-size: 12px;'>&nbsp www.adongroup.com.au</span> </a> </p></td></tr></table> </td><td width='250px'><img style='width: 250px; height: auto; float: right;' src='" +
            logoPartnerb64 +
            "' alt='Partner'/></td></tr><tr> <td colspan='3' height='40' style='line-height: 1.2; font-size: 8px;'> <p style='font-size: 8px; margin-left: 12px; margin-right: 12px; margin-bottom: 10px;'> This email, its contents and any attachments are strictly confidential. They must not be used, distributed, copied or read by any person other than the addressee. Unauthorised use, disclosure, copying or reliance on the contents of and attachments to this email by anyone other than the addressee may be unlawful. If you have received this email and attachments in error please contact us at Ad on Group immediately to facilitate its return. </p></td></tr></table> </body></html>"
        );
        openSig.document.close();
      } else {
        const openSig = document.open("", "", "fullscreen=yes");
        openSig.document.write(
          "<!DOCTYPE html PUBLIC '-//W3C//DTD XHTML 1.0 Transitional//EN' 'http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd'><html xmlns='http://www.w3.org/1999/xhtml'> <head> <meta http-equiv='Content-Type' content='text/html; charset=utf-8'/> <title>Ad On Group - Digital Marketing Specialists</title> </head> <body> <table width='650' height='170' border='0' cellspacing='0' cellpadding='0' style=' border-collapse: collapse; background: url(https://adongroup.com.au/wp-content/uploads/2022/11/bg-gradiant.png); background-repeat: no-repeat; background-size: cover; border-radius: 15px; color: white; font-family: sans-serif; line-height: 0px; font-size: 1px; padding: 0px; border-spacing: 0px; margin: 0; text-decoration: none; '> <tr> <td width='180'><img style='width: 180px; height: auto;' src='https://adongroup.com.au/wp-content/uploads/2022/11/AOG-logo.png' alt=''/></td><td> <table width='95%' height='85%' border='0' cellspacing='0' cellpadding='0' style='margin-left: 10px; margin-top: 20px;'> <tr> <td height='15' style='font-size: 15px; color: white;'><b>" +
            name +
            "</b></td></tr><tr> <td height='11' style='font-size: 11px; line-height: 1; color: white;'><b>" +
            position +
            " </b></td></tr><tr> <td height='50' style='line-height: 1.2; font-size: 10px;'> <p> <a style='text-decoration: none; color: white;' href='tel:" +
            phone +
            "'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-01.png' alt='phone'/> <span style='font-size: 12px;'>&nbsp " +
            phone +
            "</span> </a> <br/> <a style='text-decoration: none; color: white;' href='tel:" +
            mobile +
            "'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-mobile-01.png' alt='phone'/> <span style='font-size: 12px;'>&nbsp " +
            mobile +
            "</span> </a> <br/> <a style='text-decoration: none; color: white;' href='https://www.adongroup.com.au'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-02.png' alt='internet'/> <span style='font-size: 12px;'>&nbsp www.adongroup.com.au</span> </a> </p></td></tr></table> </td><td width='250px'><img style='width: 250px; height: auto; float: right;' src='" +
            logoPartnerb64 +
            "' alt='Partner'/></td></tr><tr> <td colspan='3' height='40' style='line-height: 1.2; font-size: 8px;'> <p style='font-size: 8px; margin-left: 12px; margin-right: 12px; margin-bottom: 10px;'> This email, its contents and any attachments are strictly confidential. They must not be used, distributed, copied or read by any person other than the addressee. Unauthorised use, disclosure, copying or reliance on the contents of and attachments to this email by anyone other than the addressee may be unlawful. If you have received this email and attachments in error please contact us at Ad on Group immediately to facilitate its return. </p></td></tr></table> </body></html>"
        );
        openSig.document.close();
      }
    },
    generateParadiseSignature() {
      const name = this.sigName;
      const position = this.sigPosition;
      const phone = this.sigPhone;
      const mobile = this.sigMobile;
      const logoPartnerb64 =
        "https://adongroup.com.au/wp-content/uploads/2022/11/google-partner.png";
      if (this.isShowPhone == true && this.isShowMobile == false) {
        const openSig = document.open("", "", "fullscreen=yes");
        openSig.document.write(
          "<!DOCTYPE html PUBLIC '-//W3C//DTD XHTML 1.0 Transitional//EN' 'http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd'><html xmlns='http://www.w3.org/1999/xhtml'> <head> <meta http-equiv='Content-Type' content='text/html; charset=utf-8'/> <title>Ad On Group - Digital Marketing Specialists</title> </head> <body> <table width='650' height='170' border='0' cellspacing='0' cellpadding='0' style=' border-collapse: collapse; background-color: #000000; border-radius: 15px; color: white; font-family: sans-serif; line-height: 0px; font-size: 1px; padding: 0px; border-spacing: 0px; margin: 0; text-decoration: none; '> <tr> <td width='180'><img style='width: 180px; height: auto;' src='https://adondevelopment.com/clients/2021_sig_directory/images/AOG-logo_white.png' alt=''/></td><td> <table width='95%' height='85%' border='0' cellspacing='0' cellpadding='0' style='margin-left: 10px; margin-top: 20px;'> <tr> <td height='15' style='font-size: 15px; color: white;'><b>" +
            name +
            "</b></td></tr><tr> <td height='11' style='font-size: 11px; line-height: 1; color: white;'><b>" +
            position +
            " </b></td></tr><tr> <td height='50' style='line-height: 1.2; font-size: 10px;'> <p> <a style='text-decoration: none; color: white;' href='tel:" +
            phone +
            "'> <img style='width: 10px; align-items: center;' src='https://adondevelopment.com/clients/2021_sig_directory/images/icon-01.png' alt='phone'/> <span style='font-size: 12px;'>&nbsp " +
            phone +
            "</span> </a> <br/> <a style='text-decoration: none; color: white;' href='https://www.adongroup.com.au'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-02.png' alt='internet'/> <span style='font-size: 12px;'>&nbsp www.adongroup.com.au</span> </a> </p></td></tr></table> </td><td width='250px'><img style='width: 250px; height: auto; float: right;' src='" +
            logoPartnerb64 +
            "' alt='Partner'/></td></tr><tr> <td colspan='3' height='40' style='line-height: 1.2; font-size: 8px;'> <p style='font-size: 8px; margin-left: 12px; margin-right: 12px; margin-bottom: 10px;'> This email, its contents and any attachments are strictly confidential. They must not be used, distributed, copied or read by any person other than the addressee. Unauthorised use, disclosure, copying or reliance on the contents of and attachments to this email by anyone other than the addressee may be unlawful. If you have received this email and attachments in error please contact us at Ad on Group immediately to facilitate its return. </p></td></tr></table> </body></html>"
        );
        openSig.document.close();
      } else if (this.isShowMobile == true && this.isShowPhone == false) {
        const openSig = document.open("", "", "fullscreen=yes");
        openSig.document.write(
          "<!DOCTYPE html PUBLIC '-//W3C//DTD XHTML 1.0 Transitional//EN' 'http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd'><html xmlns='http://www.w3.org/1999/xhtml'> <head> <meta http-equiv='Content-Type' content='text/html; charset=utf-8'/> <title>Ad On Group - Digital Marketing Specialists</title> </head> <body> <table width='650' height='170' border='0' cellspacing='0' cellpadding='0' style=' border-collapse: collapse; background-color: #000000; border-radius: 15px; color: white; font-family: sans-serif; line-height: 0px; font-size: 1px; padding: 0px; border-spacing: 0px; margin: 0; text-decoration: none; '> <tr> <td width='180'><img style='width: 180px; height: auto;' src='https://adondevelopment.com/clients/2021_sig_directory/images/AOG-logo_white.png' alt=''/></td><td> <table width='95%' height='85%' border='0' cellspacing='0' cellpadding='0' style='margin-left: 10px; margin-top: 20px;'> <tr> <td height='15' style='font-size: 15px; color: white;'><b>" +
            name +
            "</b></td></tr><tr> <td height='11' style='font-size: 11px; line-height: 1; color: white;'><b>" +
            position +
            " </b></td></tr><tr> <td height='50' style='line-height: 1.2; font-size: 10px;'> <p> <a style='text-decoration: none; color: white;' href='tel:" +
            mobile +
            "'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-mobile-01.png' alt='phone'/> <span style='font-size: 12px;'>&nbsp " +
            mobile +
            "</span> </a> <br/> <a style='text-decoration: none; color: white;' href='https://www.adongroup.com.au'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-02.png' alt='internet'/> <span style='font-size: 12px;'>&nbsp www.adongroup.com.au</span> </a> </p></td></tr></table> </td><td width='250px'><img style='width: 250px; height: auto; float: right;' src='" +
            logoPartnerb64 +
            "' alt='Partner'/></td></tr><tr> <td colspan='3' height='40' style='line-height: 1.2; font-size: 8px;'> <p style='font-size: 8px; margin-left: 12px; margin-right: 12px; margin-bottom: 10px;'> This email, its contents and any attachments are strictly confidential. They must not be used, distributed, copied or read by any person other than the addressee. Unauthorised use, disclosure, copying or reliance on the contents of and attachments to this email by anyone other than the addressee may be unlawful. If you have received this email and attachments in error please contact us at Ad on Group immediately to facilitate its return. </p></td></tr></table> </body></html>"
        );
        openSig.document.close();
      } else {
        const openSig = document.open("", "", "fullscreen=yes");
        openSig.document.write(
          "<!DOCTYPE html PUBLIC '-//W3C//DTD XHTML 1.0 Transitional//EN' 'http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd'><html xmlns='http://www.w3.org/1999/xhtml'> <head> <meta http-equiv='Content-Type' content='text/html; charset=utf-8'/> <title>Ad On Group - Digital Marketing Specialists</title> </head> <body> <table width='650' height='170' border='0' cellspacing='0' cellpadding='0' style=' border-collapse: collapse; background-color: #000000; border-radius: 15px; color: white; font-family: sans-serif; line-height: 0px; font-size: 1px; padding: 0px; border-spacing: 0px; margin: 0; text-decoration: none; '> <tr> <td width='180'><img style='width: 180px; height: auto;' src='https://adondevelopment.com/clients/2021_sig_directory/images/AOG-logo_white.png' alt=''/></td><td> <table width='95%' height='85%' border='0' cellspacing='0' cellpadding='0' style='margin-left: 10px; margin-top: 20px;'> <tr> <td height='15' style='font-size: 15px; color: white;'><b>" +
            name +
            "</b></td></tr><tr> <td height='11' style='font-size: 11px; line-height: 1; color: white;'><b>" +
            position +
            " </b></td></tr><tr> <td height='50' style='line-height: 1.2; font-size: 10px;'> <p> <a style='text-decoration: none; color: white;' href='tel:" +
            phone +
            "'> <img style='width: 10px; align-items: center;' src='https://adondevelopment.com/clients/2021_sig_directory/images/icon-01.png' alt='phone'/> <span style='font-size: 12px;'>&nbsp " +
            phone +
            "</span> </a> <br/> <a style='text-decoration: none; color: white;' href='tel:" +
            mobile +
            "'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-mobile-01.png' alt='phone'/> <span style='font-size: 12px;'>&nbsp " +
            mobile +
            "</span> </a> <br/> <a style='text-decoration: none; color: white;' href='https://www.adongroup.com.au'> <img style='width: 10px; align-items: center;' src='https://adongroup.com.au/wp-content/uploads/2022/11/icon-02.png' alt='internet'/> <span style='font-size: 12px;'>&nbsp www.adongroup.com.au</span> </a> </p></td></tr></table> </td><td width='250px'><img style='width: 250px; height: auto; float: right;' src='" +
            logoPartnerb64 +
            "' alt='Partner'/></td></tr><tr> <td colspan='3' height='40' style='line-height: 1.2; font-size: 8px;'> <p style='font-size: 8px; margin-left: 12px; margin-right: 12px; margin-bottom: 10px;'> This email, its contents and any attachments are strictly confidential. They must not be used, distributed, copied or read by any person other than the addressee. Unauthorised use, disclosure, copying or reliance on the contents of and attachments to this email by anyone other than the addressee may be unlawful. If you have received this email and attachments in error please contact us at Ad on Group immediately to facilitate its return. </p></td></tr></table> </body></html>"
        );
        openSig.document.close();
      }
    },
  },
};
</script>
<style scoped>
.radio-group {
  display: flex;
  flex-direction: column;
  gap: 10px;
  padding: 1rem;
  background-color: var(--light);
  border-radius: var(--corner-radius);
  /* box-shadow: var(--shadow); */
}
.user-input {
  width: 100%;
  height: 2rem;
  text-indent: 0.5rem;
  border: none;
  border-bottom: 1px solid var(--dark);
}
.signature-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.signature-container {
  width: 30%;
  padding: 1.5rem;
  background-color: white;
  box-shadow: var(--shadow);
  border-radius: var(--corner-radius);
}
.view-container {
  width: 70%;
  padding: 1.5rem;
  background-color: white;
  box-shadow: var(--shadow);
  border-radius: var(--corner-radius);
}

.signature-data {
  background-color: var(--dark);
  background: url("https://adongroup.com.au/wp-content/uploads/2022/11/bg-gradiant.png");
  background-repeat: no-repeat;
  background-size: cover;
  border-radius: 0.5rem;
  padding: 10px;
  width: 100%;
  height: auto;
}
.signature-data-paradise {
  background-color: var(--dark);
  /* background-image: linear-gradient(#07031E, #00057B); */
  background-image: url("https://adongroup.com.au/wp-content/uploads/2022/11/bg-gradiant.png");
  background-repeat: no-repeat;
  background-size: cover;
  border-radius: 0.5rem;
  padding: 10px;
  width: 100%;
  height: auto;
}
.data {
  display: flex;
  flex-direction: row;
  gap: 1.5rem;
  align-items: center;
}
/* .logo-aog {
  width: 30%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: start;
  color: #ffffff;
  gap: .5rem;
}
.logo-aow {
  width: 30%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: start;
  color: #ffffff;
  gap: .5rem;
}
.logo-aog img {
  width: 100%;
}
.logo-aow img {
  width: 100%;
  margin-top: -3rem;
}

.logo-aow strong {
  font-size: 12px;
}

.logo-aog strong {
  font-size: 12px;
} */
.info {
  width: 30%;
  color: var(--white);
}
.info strong {
  font-size: 0.8rem;
}
.info p {
  font-size: 0.8rem;
}
.info .links {
  font-size: 0.6rem;
  margin-top: 10px;
}
.info p a img {
  width: 0.5rem;
}
.info p a {
  text-decoration: none;
  color: var(--white);
}
.partner {
  width: 30%;
  /* padding-top: 1rem; */
}
.partner img {
  width: 100%;
}
.disclaimer {
  color: var(--white);
}
.disclaimer p {
  font-size: 0.4rem;
  line-height: 1.2;
}
.action-btn {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 5px;
}
.my-card {
  background-color: white;
  border-radius: .5rem;
  padding: 1rem;
  box-shadow: 0 0 40px 0 rgba(0, 0, 0,.15);
}
.logo-aog-aow {
    width: 100%;
}
</style>
