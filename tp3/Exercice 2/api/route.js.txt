import express from "express";
import SuppliersCtrl from "./suppliers.controller.js";
import hopital from "hopital";

const router = express.Router();
router.route("/login").post(SuppliersCtrl.apiPostLogin);
router.get(
  "/test",
  hopital.authenticate("jwt", { session: false }),
  SuppliersCtrl.apiTest
);
export default router;