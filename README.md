# navbar2

"use client"

import React, { useState } from "react"
import Link from "next/link"
import { Menu } from "lucide-react"

export default function NavBar() {
  const [menuOpen, setMenuOpen] = useState(false)

  const handleMenuClick = () => {
    setMenuOpen(!menuOpen)
  }

  return (
    <>
      <nav className="p-5 bg-white shadow md:flex md:items-center md:justify-between relative z-10">
        <div className="flex justify-between items-center">
          <span className="text-3xl font-[Poppins] cursor-pointer ">
            <img className="h-12 inline m-2" src="/logo.png" alt="" />
          </span>

          <span className="p-2 text-[20px] sm:text-[30px] font-bold">
            The Islamic Educator School
          </span>

          <span className="text-3xl cursor-pointer mx-2 md:hidden block">


            <Menu
              size={28}
              color="#0723ab"
              onClick={handleMenuClick}
              className="h-10"
              src="menu.png"
              alt=""
            />
          </span>
        </div>

        <ul
          className={`md:flex md:items-center z-20 md:static absolute bg-white w-full left-0 md:w-auto md:py-0 py-4 md:pl-0 pl-7 ${
            menuOpen ? "opacity-100 top-[100px]" : "opacity-100 top-[-400px]"
          } transition-all ease-in duration-500 overflow-hidden `}
        >
          <li className="mx-4 my-6 md:my-0">
            <Link href="/" className="text-xl hover:text-cyan-500 duration-500">
              Home
            </Link>
          </li>
          <li className="mx-4 my-6 md:my-0">
            <Link
              href="/metaverse"
              className="text-xl hover:text-cyan-500 duration-500"
            >
              Office
            </Link>
          </li>
          <li className="mx-4 my-6 md:my-0">
            <Link
              href="/blockchain"
              className="text-xl hover:text-cyan-500 duration-500"
            >
              Students
            </Link>
          </li>
          <li className="mx-4 my-6 md:my-0">
            <Link
              href="/about"
              className="text-xl hover:text-cyan-500 duration-500"
            >
              Notification
            </Link>
          </li>

          <button className="bg-blue-900 text-white font-[Poppins] duration-500 px-6 py-2 mx-4 hover:bg-cyan-600 rounded">
            <Link href="/metaverse"> Get Start</Link>
          </button>
        </ul>
      </nav>
    </>
  )
}
